# 🛠️ OpenCode Skills Collection

> A curated collection of **131+ Agent Skills** for [OpenCode](https://opencode.ai) — ready to drop into your `~/.config/opencode/skills/` directory and supercharge your coding agent across CLI and Desktop.

[![OpenCode](https://img.shields.io/badge/OpenCode-Skills-purple?style=for-the-badge)](https://opencode.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Total Skills](https://img.shields.io/badge/Skills-131+-blue?style=for-the-badge)](https://github.com/carlo/My-Skills)
[![Platform](https://img.shields.io/badge/Platform-CLI%20%7C%20Desktop-green?style=for-the-badge)](https://opencode.ai)

---

## 📖 About

This repository contains a personal collection of OpenCode skills gathered from multiple sources, including:

- **[farmage/opencode-skills](https://github.com/farmage/opencode-skills)** — 67 specialized skills across 12 domains (languages, frameworks, infrastructure, architecture, and more)
- **[anthropics/skills](https://github.com/anthropics/skills)** — Official Anthropic production skills (docx, pdf, pptx, xlsx, claude-api, mcp-builder, and more)
- **[obra/superpowers](https://github.com/obra/superpowers)** — The Superpowers methodology skills (brainstorming, systematic-debugging, test-driven-development, writing-plans, and more)
- **[nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)** — UI/UX design intelligence with 80+ styles, 194 color palettes, and design system generation
- **[mattpocock/skills](https://github.com/mattpocock/skills)** — Real engineering skills: grill-with-docs, to-spec, to-tickets, tdd, code-review, wayfinder, retro, and more
- **[abhigyanpatwari/GitNexus](https://github.com/abhigyanpatwari/GitNexus)** — Code graph intelligence skills for impact analysis, debugging, refactoring, and PR review
- **Custom skills** — youtube-transcript and other personal additions

All skills are drop-in compatible with OpenCode CLI and OpenCode Desktop. Just copy the skill folders into your OpenCode skills directory and restart.

---

## 🚀 Quick Start

### 1. Clone this repository

```bash
git clone https://github.com/carlo/My-Skills.git
cd My-Skills
```

### 2. Install skills into OpenCode

Copy all skill folders into your OpenCode skills directory:

**Windows (PowerShell):**
```powershell
Copy-Item -Path ".\*" -Destination "$env:USERPROFILE\.config\opencode\skills\" -Recurse -Force
```

**macOS / Linux:**
```bash
cp -r * ~/.config/opencode/skills/
```

### 3. Restart OpenCode

Restart both **OpenCode CLI** and **OpenCode Desktop** to activate all skills.

### 4. Verify installation

```powershell
Get-ChildItem -Path "$env:USERPROFILE\.config\opencode\skills" -Directory | Measure-Object
```

You should see **131+ skill directories**.

---

## 📦 Skills by Category

### 🔤 Languages (15)
| Skill | Description |
|-------|-------------|
| `python-pro` | Python 3.11+ applications with type safety and async |
| `typescript-pro` | Advanced TypeScript type systems and tRPC |
| `javascript-pro` | Modern ES2023+ JavaScript and Node.js |
| `go` / `golang-pro` | Concurrent Go patterns and microservices |
| `rust-engineer` | Idiomatic Rust with memory safety |
| `cpp-pro` | Modern C++20/23 systems programming |
| `csharp-developer` | .NET 8+ and ASP.NET Core |
| `dotnet-core-expert` | .NET 8 clean architecture and microservices |
| `java-architect` | Spring Boot 3.x enterprise Java |
| `kotlin-specialist` | Kotlin coroutines and multiplatform |
| `swift-expert` | iOS/macOS SwiftUI and Swift |
| `php-pro` | Modern PHP 8.3+ and Laravel |
| `ruby` | Ruby development |
| `sql-pro` | SQL optimization and schema design |
| `dart` | Dart and Flutter |

### 🌐 Frontend & Web (12)
| Skill | Description |
|-------|-------------|
| `react-expert` | React 18+ components and hooks |
| `nextjs-developer` | Next.js 14+ App Router |
| `vue-expert` / `vue-expert-js` | Vue 3 Composition API |
| `angular-architect` | Angular 17+ standalone components |
| `svelte` | Svelte components |
| `html-tailwind` | HTML + Tailwind CSS |
| `shadcn` | shadcn/ui components |
| `frontend-design` | Distinctive visual design |
| `ui-ux-pro-max` | UI/UX design intelligence |
| `theme-factory` | Artifact theming toolkit |
| `web-artifacts-builder` | React + Tailwind artifacts |
| `webapp-testing` | Playwright E2E testing |

### ☁️ Backend & APIs (10)
| Skill | Description |
|-------|-------------|
| `nestjs-expert` | NestJS enterprise backends |
| `django-expert` | Django and Django REST Framework |
| `fastapi-expert` | High-performance FastAPI |
| `spring-boot-engineer` | Spring Boot 3.x |
| `rails-expert` | Rails 7+ Hotwire |
| `laravel-specialist` | Laravel 10+ |
| `api-designer` | REST and GraphQL API design |
| `graphql-architect` | GraphQL schemas and federation |
| `microservices-architect` | Distributed system design |
| `cloud-architect` | AWS, Azure, GCP architectures |

### 📱 Mobile & Desktop (6)
| Skill | Description |
|-------|-------------|
| `react-native-expert` | React Native and Expo |
| `flutter-expert` | Flutter 3+ and Dart |
| `flutter` | Flutter development |
| `kotlin-specialist` | Android Kotlin |
| `swift-expert` | iOS SwiftUI |
| `game-developer` | Unity and Unreal Engine |

### 🏗️ Infrastructure & DevOps (12)
| Skill | Description |
|-------|-------------|
| `devops-engineer` | Docker, Kubernetes, CI/CD |
| `kubernetes-specialist` | K8s workloads and Helm |
| `terraform-engineer` | Infrastructure as Code |
| `docker` | Containerization |
| `sre-engineer` | SLOs, error budgets, reliability |
| `chaos-engineer` | Chaos engineering and resilience |
| `monitoring-expert` | Prometheus, Grafana, observability |
| `devops` | DevOps practices |
| `cloud-architect` | Multi-cloud design |
| `ansible` | Configuration management |
| `jenkins` | CI/CD pipelines |
| `gitlab-ci` | GitLab CI/CD |

### 🗄️ Data & Databases (8)
| Skill | Description |
|-------|-------------|
| `postgres-pro` | PostgreSQL optimization |
| `database-optimizer` | Query and index optimization |
| `sql-pro` | SQL schema and queries |
| `mongodb` | MongoDB |
| `redis` | Redis caching |
| `elasticsearch` | Search and analytics |
| `pandas-pro` | pandas DataFrame analysis |
| `ml-pipeline` | ML infrastructure and MLOps |

### 🔒 Security & Quality (8)
| Skill | Description |
|-------|-------------|
| `security-reviewer` | Security audits and SAST |
| `secure-code-guardian` | Authentication and OWASP Top 10 |
| `code-reviewer` | Two-axis code review |
| `code-documenter` | Technical documentation |
| `test-master` | Test strategies and QA |
| `tdd` | Test-driven development |
| `diagnosing-bugs` | Systematic debugging |
| `systematic-debugging` | Root cause analysis |

### 🏗️ Architecture & Process (12)
| Skill | Description |
|-------|-------------|
| `architecture-designer` | High-level system design |
| `codebase-design` | Deep module design |
| `improve-codebase-architecture` | Architecture deepening |
| `writing-plans` | Implementation planning |
| `to-spec` | Spec generation |
| `to-tickets` | Tracer-bullet tickets |
| `implement` / `implement-spec` | Plan execution |
| `wayfinder` | Large effort mapping |
| `retro` | Session retrospectives |
| `feature-forge` | Feature specifications |
| `spec-miner` | Legacy code reverse engineering |
| `legacy-modernizer` | Legacy system migration |

### 🤖 AI & ML (8)
| Skill | Description |
|-------|-------------|
| `claude-api` | Claude API and Anthropic SDK |
| `mcp-builder` | MCP server development |
| `mcp-developer` | MCP clients and servers |
| `rag-architect` | RAG systems and vector stores |
| `fine-tuning-expert` | LLM fine-tuning (LoRA, QLoRA) |
| `prompt-engineer` | LLM prompt engineering |
| `ml-pipeline` | MLOps and experiment tracking |
| `fine-tuning` | Model training |

### 🛠️ Productivity & Workflow (12)
| Skill | Description |
|-------|-------------|
| `brainstorming` | Idea exploration |
| `grill-with-docs` / `grill-me` | Relentless design interview |
| `domain-modeling` | Glossary and ADRs |
| `domain-model` | Domain language |
| `handoff` | Session handoff documents |
| `teach` | Multi-session teaching |
| `wait-what` | Message clarification |
| `writing-for-agents` | Agent documentation |
| `skill-creator` | Create new skills |
| `the-fool` | Devil's advocate reasoning |
| `hand-off` | Context transfer |
| `setup-matt-pocock-skills` | Matt Pocock skills setup |

### 🔍 GitNexus Code Graph (13)
| Skill | Description |
|-------|-------------|
| `gitnexus-guide` | GitNexus tools and schema reference |
| `gitnexus-cli` | CLI commands (analyze, status, wiki) |
| `gitnexus-exploring` | Codebase exploration |
| `gitnexus-debugging` | Bug tracing and root cause |
| `gitnexus-impact-analysis` | Blast radius analysis |
| `gitnexus-refactoring` | Safe refactoring and renaming |
| `gitnexus-review` | PR review workflow |
| `gitnexus-plan` | Implementation planning |
| `gitnexus-work` | Plan execution |
| `gitnexus-lfg` | Plan → gate → work → review pipeline |
| `gitnexus-pr-swarm-review` | PR swarm review |
| `pr-tri-review` | Multi-engine PR review |
| `gitnexus-work` | Plan executor |

### 🎨 Design & UX (4)
| Skill | Description |
|-------|-------------|
| `ui-ux-pro-max` | UI/UX design intelligence |
| `frontend-design` | Visual design guidance |
| `canvas-design` | Visual art creation |
| `theme-factory` | Theming toolkit |

### 📄 Documents & Office (4)
| Skill | Description |
|-------|-------------|
| `docx` | Word document creation and editing |
| `pdf` | PDF processing |
| `pptx` | PowerPoint presentations |
| `xlsx` | Spreadsheet creation and analysis |

### ⚡ Superpowers (16)
| Skill | Description |
|-------|-------------|
| `using-superpowers` | Superpowers system introduction |
| `brainstorming` | Pre-build exploration |
| `systematic-debugging` | Debugging methodology |
| `test-driven-development` | Red-green-refactor |
| `writing-plans` | Planning methodology |
| `executing-plans` | Inline plan execution |
| `subagent-driven-development` | Parallel subagent workflow |
| `code-review` | Code review |
| `receiving-code-review` | Review feedback handling |
| `requesting-code-review` | Review requests |
| `dispatching-parallel-agents` | Concurrent tasks |
| `finishing-a-development-branch` | Branch completion |
| `verification-before-completion` | Evidence before claims |
| `diagnosing-superpowers` | Session diagnosis |
| `test-master` | Test mastery |
| `codebase-design` | Deep module design |

### 🎬 Miscellaneous (5)
| Skill | Description |
|-------|-------------|
| `youtube-transcript` | YouTube transcript extraction |
| `slack-gif-creator` | Slack-optimized GIFs |
| `mcp-developer` | MCP development |
| `websocket-engineer` | Real-time WebSocket systems |
| `spark-engineer` | Apache Spark |

---

## 🗂️ Repository Structure

```
My-Skills/
├── README.md
├── LICENSE
├── .gitignore
├── academy-guide/
│   └── SKILL.md
├── python-pro/
│   └── SKILL.md
├── typescript-pro/
│   └── SKILL.md
├── ...
└── youtube-transcript/
    ├── SKILL.md
    └── scripts/
        ├── extract-transcript-segments.py
        ├── get-languages.py
        └── open-transcript-panel.py
```

Each skill folder contains:
- **`SKILL.md`** — The skill instructions with YAML frontmatter (`name`, `description`, etc.)
- **`scripts/`** — Optional helper scripts (Python, etc.)
- **`references/`** — Optional reference documents

---

## ⚙️ How Skills Work in OpenCode

OpenCode discovers skills in two locations:

```
~/.config/opencode/skills/<name>/SKILL.md    # Global (all projects)
.opencode/skills/<name>/SKILL.md             # Project-local
```

Skills activate **automatically** based on your message content. You can also invoke them manually using the `skill` tool:

```
skill: typescript-pro
```

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-skill`)
3. Commit your changes (`git commit -m 'Add: amazing skill'`)
4. Push to the branch (`git push origin feature/amazing-skill`)
5. Open a Pull Request

Please ensure each skill includes:
- A valid `SKILL.md` with `name` and `description` frontmatter
- Clear "When to Use" examples
- No sensitive information or secrets

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## ⭐ Acknowledgments

Special thanks to the creators of the original skill repositories:

- [farmage/opencode-skills](https://github.com/farmage/opencode-skills)
- [anthropics/skills](https://github.com/anthropics/skills)
- [obra/superpowers](https://github.com/obra/superpowers)
- [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill)
- [mattpocock/skills](https://github.com/mattpocock/skills)
- [abhigyanpatwari/GitNexus](https://github.com/abhigyanpatwari/GitNexus)

---

<div align="center">

**Built with ❤️ for the OpenCode community**

[⬆️ Back to top](#opencode-skills-collection)

</div>