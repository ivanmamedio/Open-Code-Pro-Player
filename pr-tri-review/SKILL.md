---
name: pr-tri-review
description: "Review a GitHub PR with three review methods (GitNexus PR swarm + ce-code-review personas + Codex adversarial), then a synthesis agent merges everything, a synthesis critic gates the result, and it posts as one inline-comment review."
---

# PR Tri-Review

Runs the same two review methodologies on both engines (Claude and Codex), plus a Codex adversarial pass. A Claude synthesis agent merges all results; `gitnexus-synthesis-critic` gates the digest before posting.

```
/pr-tri-review <PR number or URL>
```

## Phases

### Phase 1 — Scope
- Derive repo and PR facts (`$REPO` = base repo via `gh repo view`)
- Run idempotency probe: check if this skill already posted a review (`<!-- pr-tri-review -->`)
- Fetch PR code locally via worktree (`git worktree add`)
- Create artifact dir `$ART=/tmp/pr-tri-review/<PR>/<RUN_ID>` to persist every lane
- Compute accurate diff base `BASE` via `git merge-base`
- Sanity-check base by file count vs PR file count
- Run prior-context recall (claude-mem)

### Phase 2 — Assemble lanes

**Engine A (Claude):**
- A1 — GitNexus PR swarm (Swarm mode, parallel `gitnexus-*` subagents)
- A2 — ce-code-review (condition-based reviewers)

**Engine B (Codex, `$CODEX_MODEL` / xhigh):**
- B1 — GitNexus PR swarm (Solo mode)
- B2 — ce-code-review (report-only mode)
- B3 — native Codex adversarial-review

All five lanes are independent engines reading same scaffolding.

### Phase 3 — Dispatch all lanes (read-only) and persist to disk

- Launch Engine B (Codex) first via `codex-companion.mjs` directly
- Dispatch Engine A (Claude) lanes in parallel via subagents
- Every agent prompt starts with `[independent-lane]`
- Every lane writes full output to `$ART/<engine>-<lane>.md`
- Exit markers: `echo $? > $ART/codex-<leg>.exit`

### Phase 4 — Synthesis → coordinator verify → critic gate

4.1 — Dedicated Claude synthesis agent reads all `$ART/*.md`, produces `$ART/digest-draft.md`
   - Weight by cross-engine corroboration (Codex agreeing with Claude = strong signal)
   - Severity overrides corroboration (single-lane P0/P1 with concrete trigger is postable)
   - Per-finding verification: trigger + evidence + tag `[reproduced]` or `[code-read]`
   - Drop refuted findings; dedup by file+line+theme
   - Check each Codex artifact liveness

4.2 — Coordinator re-reads every `[code-read]` finding; drop what can't be verified

4.3 — `gitnexus-synthesis-critic` gates `$ART/digest-draft.md`
   - Hard gate: don't post while corrections list is non-empty
   - Critic is bounded to two passes

### Phase 5 — Post one review

- Re-check idempotency probe
- Build single review via GitHub reviews API (`event: "COMMENT"`)
- Body starts with `<!-- pr-tri-review -->` signature
- Inline comments require Phase-4 verification; anchor only to diff lines
- Confirm comments attached via `gh api .../comments`

## Cross-engine corroboration rule

The strong signal: a **Codex lane agreeing with a Claude lane** (different engine, same review contract).
Agreement *within* one engine is "consistent," not independent confirmation — can be shared false positive.

## Output

Lead with findings in severity order. Verdict: APPROVE | REQUEST CHANGES | NEEDS DISCUSSION.
Include exact target SHAs so a later run can tell whether evidence is stale.
