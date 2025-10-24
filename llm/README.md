Purpose: Explain the llm/ docs workspace and its project/context/workflows structure.

# LLM Docs Workspace

This folder is the source of truth for project planning and repeatable guidance used by humans and agents. It now follows a three-part structure: `project/`, `context/`, and `workflows/`.

## Structure

```
llm/
├── README.md                  # You are here — how this workspace works
├── project/                   # Canonical project plan and phases
│   ├── project-overview.md    # Your project definition (create from example)
│   ├── user-flow.md           # User journeys and states
│   ├── tech-stack.md          # Technology choices and conventions
│   ├── design-rules.md        # Visual language, accessibility, components
│   ├── project-rules.md       # Coding standards and workflows
│   └── phases/                # Iterative delivery plans
│       ├── setup-phase.md
│       ├── mvp-phase.md
│       └── [additional-phase].md
├── context/                   # Focused, reusable references for implementation
│   └── (e.g.) nostr-nip-01.md, ui-tokens.md, security-model.md
└── workflows/                 # Repeated operational runbooks
    └── dev-env-local.md       # Default: set up local dev environment
```

## Folder Intent
- `project/` — Everything about the product plan: overview, user flows, tech stack, design rules, engineering standards, and the phased roadmap.
- `context/` — Tight, implementation-oriented briefs. Examples: a protocol spec summary you’ll cite in prompts (e.g., `nostr-nip-01.md`), a domain model, or a library’s usage patterns.
- `workflows/` — Common runbooks you’ll reuse across releases (e.g., local dev setup, release process, code signing, incident response).

## Conventions
- Begin each file with a single-line purpose note; keep files under 500 lines.
- Use descriptive kebab-case filenames. Prefer short, linkable documents over mega files.
- Update `project/` first; add supporting `context/` docs and `workflows/` as the project evolves.

## Quick Start
1. Open `llm/project/setup.md` and follow the steps to generate your baseline docs.
2. Copy `llm/project/project-overview-example.md` to `llm/project/project-overview.md` and tailor it.
3. Add any relevant specs to `llm/context/` (e.g., `nostr-nip-01.md`).
4. Use `workflows/dev-env-local.md` to get the environment running on a fresh machine.

## Migration Note
As of 2025-10-22, all prior top-level `llm/*` docs live under `llm/project/`. Update any local references to the new paths.

