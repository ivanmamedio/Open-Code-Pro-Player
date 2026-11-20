---
name: gitnexus-pr-swarm-review
description: "Run a GitNexus production-readiness pull request review using a coordinated reviewer swarm."
---

# GitNexus PR Swarm Review (Claude Code adapter)

Use this skill to review a GitNexus pull request and produce a production-readiness review.

> This is the interactive, on-demand reviewer swarm. It is distinct from the CI
> `gitnexus-review` skill's built-in "Swarm lanes" (`ci-personas/`), which the
> review-agent workflow dispatches automatically inside a single review run.

```
/gitnexus-pr-swarm-review <PR URL or PR number>
```

You are the **swarm coordinator**. The full review contract — lanes, dependencies,
classifications, output structure, finding format, hidden-Unicode checks, and behavior
rules — is the canonical, CLI-neutral spec:

**`pr-swarm-review/orchestration.md`** — read it now and follow it.

This adapter only pins the Claude Code specifics:

- **Run in Swarm mode.** Dispatch each lane as its own subagent via the Agent tool. The
  seven subagents are the project agents named `gitnexus-*` (one per persona); each reads
  its canonical persona under `pr-swarm-review/personas/`. Run lanes 1–2 first, lanes 3–6
  in parallel after, and lane 7 last on the draft.
- **Lane 7 is a hard gate.** Do not emit the final review while the synthesis critic's
  "Required corrections before posting" section is non-empty — revise and re-run it.
- Stay **read-only**: investigate and report; never edit, commit, or post.

Do not flatten the review into a generic checklist; delegate to the subagents and
synthesize per `orchestration.md`.

## Lanes

| Lane | Role |
|------|------|
| gitnexus-pr-facts-historian | PR facts, history, linked issues |
| gitnexus-branch-hygiene-reviewer | Branch hygiene checks |
| gitnexus-risk-architect | Risk architecture review |
| gitnexus-test-ci-verifier | Test & CI verification |
| gitnexus-security-boundary-reviewer | Security boundary review |
| gitnexus-docs-dod-reviewer | Docs & Definition of Done |
| gitnexus-synthesis-critic | Synthesis critic (gate) |

## How to run

1. **Read `pr-swarm-review/orchestration.md`** for the full contract.
2. **Dispatch lanes 1–2 first** (they set up context for the rest).
3. **Dispatch lanes 3–6 in parallel** — each as its own subagent via the `skill` tool with `gitnexus-*` id.
4. **Dispatch lane 7 last** on the draft review — it's a hard gate.
5. **Synthesize** all lane findings into one review.
6. **Do not emit** while lane 7's corrections list is non-empty.
7. **Stay read-only** — never edit, commit, push, or post.

## Important notes

- Each lane reads its canonical persona under `pr-swarm-review/personas/`.
- Run lanes 1–2 first, then 3–6 in parallel, then 7 last.
- Lane 7 (synthesis critic) is mandatory before any final review output.
- Do not flatten into a generic checklist — delegate to subagents and synthesize per the contract.
