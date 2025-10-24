Purpose: Runbook to generate baseline docs using the project/context/workflows layout.

# Project Setup Guide

Use this runbook to generate the documentation baseline before any coding. Complete each step in order—the outputs cascade into later prompts. All project docs live in `llm/project/`; supporting references go in `llm/context/`; repeatable runbooks go in `llm/workflows/`.

## Quick Start
- Prerequisites: Node.js 20+, npm. See `llm/workflows/dev-env-local.md` if you need local setup.
- Copy the template to begin: `llm/project/project-overview-example.md` → `llm/project/project-overview.md`.
- Keep files under 500 lines and start each with a one-line purpose note.

## Context and Workflows
- Add focused references in `llm/context/` when you need concise specs or implementation notes you’ll cite during prompts (e.g., `nostr-nip-01.md`).
- Use `llm/workflows/dev-env-local.md` for repeatable setup; add more runbooks (e.g., release process) as the project grows.

## Phase 1 — Project Foundation

### Step 1 — Project Overview
- **Deliverable:** `llm/project/project-overview.md`
- **Capture:** purpose, goals, audience, primary features, guardrails.
- **Prompt:**
```
Create llm/project/project-overview.md defining the project's purpose, scope, target audience, primary features, and measurable goals.
Ask clarifying questions instead of guessing.
```

### Step 2 — User Flow
- **Deliverable:** `llm/project/user-flow.md`
- **Capture:** end-to-end journey, major states, key actions per user persona.
- **Prompt:**
```
Use @llm/project/project-overview.md to draft `user-flow.md` that maps each persona through the experience.
Detail screen/state transitions and decision points.
```

### Step 3 — Tech Stack
- **Deliverable:** `llm/project/tech-stack.md`
- **Prep:** Decide technologies you already favour (e.g. TypeScript, Next.js, Supabase) and consult the [AI Dev Program freedom-tech guide](https://github.com/pleb-devs/freedom-tech) for complementary sovereign-focused options.
- **Prompt:**
```
Use @llm/project/project-overview.md, @llm/project/user-flow.md, and the AI Dev Program freedom-tech guide (https://github.com/pleb-devs/freedom-tech; paste excerpts if the agent cannot access) to recommend a tech stack. I already want to use [LIST YOUR PREFERRED TECHNOLOGIES HERE].
For each layer, provide one primary choice and one alternative with trade-offs, noting where freedom-tech options strengthen sovereignty/security.
```

### Step 4 — Stack Best Practices
- **Deliverable Update:** Enrich `llm/project/tech-stack.md` with usage notes, pitfalls, conventions, and references to guidance from the freedom-tech catalog where it genuinely helps.
- **Prompt:**
```
Update @llm/project/tech-stack.md with best practices, common pitfalls, and usage conventions for each selected technology. Highlight insights from the freedom-tech catalog when they strengthen recommendations.
```

## Phase 2 — Design Guidelines

### Step 5 — Design Principles
- **Deliverable:** Research notes or inline summary for `llm/project/design-rules.md`.
- **Prompt:**
```
Using @llm/project/project-overview.md and @llm/project/user-flow.md, outline design principles that fit this product. Suggest 2–3 visual styles (e.g., minimalist, glassmorphic) with quick rationale.
```

### Step 6 — Design Rules
- **Deliverable:** `llm/project/design-rules.md`
- **Customize:** Add your chosen tone (mobile-first, animated, minimalist, etc.).
- **Prompt:**
```
I want the project to be [DESIGN DIRECTION].
Using @llm/project/project-overview.md, @llm/project/user-flow.md, and @llm/project/tech-stack.md, create `design-rules.md` covering:
- Design principles and accessibility guardrails
- Color palette and typography
- Component styling conventions
- Spacing, layout, and interaction patterns
```

## Phase 3 — Project Rules

### Step 7 — Engineering Standards
- **Deliverable:** `llm/project/project-rules.md`
- **Focus:** directory map, file naming, code documentation, workflow standards.
- **Prompt:**
```
We are building an AI-first codebase that must stay modular, readable, and well documented. Files need descriptive headers, functions require JSDoc/TSDoc, and individual files should stay under 500 lines.
Using @llm/project/tech-stack.md, @llm/project/user-flow.md, @llm/project/project-overview.md, and @llm/project/design-rules.md, draft `project-rules.md` with:
- Directory structure and naming conventions
- Code organisation patterns and documentation rules
- Development workflow expectations
```

## Phase 4 — Delivery Planning

### Step 8 — Phased Roadmap
- **Deliverables:** `llm/project/phases/setup-phase.md`, `llm/project/phases/mvp-phase.md`, plus any follow-up phases.
- **Prompt:**
```
Create an iterative development plan from setup to MVP to advanced phases.
Rules:
- Setup = barebones but running
- MVP = core value delivered
- Later phases = enhancements, scale, polish
- Each phase goes in its own document with scope and 3–5 actionable steps per feature
- Plans must build on the previous phase and remain shippable

Use @llm/project/project-overview.md, @llm/project/user-flow.md, @llm/project/tech-stack.md, and @llm/project/project-rules.md for context.
Place the files in `llm/project/phases/`.
```

## Phase 5 — Development Enablement

### Step 9 — Agent Rules
- **Deliverable:** Copy into Cursor User Rules or team handbook.
- **Why:** Keep every assistant aligned with the engineering expectations.
- **Paste:**
```
You are an expert in TypeScript, Node.js, NextJS + App Router, React, Shadcn, Radix UI, and Tailwind CSS.
You have extensive experience building production-grade applications for large companies.
You specialize in clean, scalable architectures for complex codebases.
Never assume the user is correct; probe for clarity.
Always review existing files before generating new ones.

We are building an AI-first codebase: modular, scalable, readable. The structure must be highly navigable.
All files require descriptive names, a short header explaining contents, and documented functions (JSDoc/TSDoc/etc.). Keep files under 500 lines.

Code Style and Structure:
- Write concise, technical code.
- Prefer functional/declarative patterns over classes.
- Add descriptive block comments to functions.
- Favour iteration and modularisation over duplication.
- Throw errors instead of silent fallbacks.
- Use descriptive variables with auxiliary verbs (isLoading, hasError).
- Avoid enums; use maps.
- Use the `function` keyword for pure functions.
- Keep conditionals lean; avoid redundant braces.
```

Note: Also see `AGENTS.md` at the repo root for shared standards.

### Step 10 — README Refresh
- **Deliverable:** Updated project README.
- **Prompt:**
```
Using @llm/project/project-overview.md, @llm/project/user-flow.md, @llm/project/tech-stack.md, and @llm/project/project-rules.md, refresh the README with a concise project summary and key conventions.
```

### Step 11 — Documentation Audit
Confirm `llm/` contains the full set in the new layout:
- `llm/project/project-overview.md`
- `llm/project/user-flow.md`
- `llm/project/tech-stack.md`
- `llm/project/design-rules.md`
- `llm/project/project-rules.md`
- `llm/project/phases/setup-phase.md`
- `llm/project/phases/mvp-phase.md`
- `llm/project/phases/[additional-phase].md`
- `llm/context/[any-supporting-context].md`
- `llm/workflows/dev-env-local.md`

### Step 12 — Kickoff Prompt
- **Deliverable:** First development task or pairing session.
- **Prompt:**
```
Let's get started on our project.
```
- **Attach:** Agent Rules, `llm/project/phases/setup-phase.md`, `llm/project/tech-stack.md`, and `llm/project/project-overview.md` (and `llm/workflows/dev-env-local.md`) to keep the assistant grounded.

## Tips for Success
- Iterate on earlier docs as new insights emerge.
- Ask clarifying questions instead of guessing requirements.
- Keep prompts and outputs in sync—update documentation when decisions change.
- Store everything in `llm/` (primarily `llm/project/`) so contributors and agents have a single source of truth.

## Directory Quick Reference
```
llm/
├── README.md
├── project/
│   ├── project-overview.md
│   ├── user-flow.md
│   ├── tech-stack.md
│   ├── design-rules.md
│   ├── project-rules.md
│   └── phases/
│       ├── setup-phase.md
│       ├── mvp-phase.md
│       └── [additional-phase].md
├── context/
│   └── [supporting-context].md
└── workflows/
    └── dev-env-local.md
```
