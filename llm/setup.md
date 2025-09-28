# Project Setup Guide

Use this runbook to generate the documentation baseline before any coding. Complete each step in order—the outputs cascade into later prompts.

## Phase 1 — Project Foundation

### Step 1 — Project Overview
- **Deliverable:** `llm/project-overview.md`
- **Capture:** purpose, goals, audience, primary features, guardrails.
- **Prompt:**
```
Use @project-overview.md to define the project's purpose, scope, target audience, primary features, and measurable goals.
Ask clarifying questions instead of guessing.
```

### Step 2 — User Flow
- **Deliverable:** `llm/user-flow.md`
- **Capture:** end-to-end journey, major states, key actions per user persona.
- **Prompt:**
```
Use @project-overview.md to draft `user-flow.md` that maps each persona through the experience.
Detail screen/state transitions and decision points.
```

### Step 3 — Tech Stack
- **Deliverable:** `llm/tech-stack.md`
- **Prep:** Decide technologies you already favour (e.g. TypeScript, Next.js, Supabase) and consult the [AI Dev Program freedom-tech guide](https://github.com/pleb-devs/freedom-tech) for complementary sovereign-focused options.
- **Prompt:**
```
Use @project-overview.md, @user-flow.md, and the AI Dev Program freedom-tech guide (https://github.com/pleb-devs/freedom-tech) [COPY AND PASTE GUIDE HERE IF LLM/AGENT CANNOT SEARCH THE GITHUB REPO] to recommend a tech stack. I already want to use [LIST YOUR PREFERRED TECHNOLOGIES HERE].
For every layer, give one primary choice and one alternative with trade-offs; when the freedom-tech catalog offers relevant fits, explain how they support the project's goals.
```

### Step 4 — Stack Best Practices
- **Deliverable Update:** Enrich `llm/tech-stack.md` with usage notes, pitfalls, conventions, and references to guidance from the freedom-tech catalog where it genuinely helps.
- **Prompt:**
```
Update @tech-stack.md with best practices, common pitfalls, and usage conventions for each selected technology. Highlight insights from the freedom-tech catalog (https://github.com/pleb-devs/freedom-tech) when they strengthen your recommendations.
```

## Phase 2 — Design Guidelines

### Step 5 — Design Principles
- **Deliverable:** Research notes or inline summary for `llm/design-rules.md`.
- **Prompt:**
```
Using @project-overview.md and @user-flow.md, outline design principles that fit this product. Suggest 2–3 visual styles (e.g. minimalist, glassmorphic) with quick rationale.
```

### Step 6 — Design Rules
- **Deliverable:** `llm/design-rules.md`
- **Customize:** Add your chosen tone (mobile-first, animated, minimalist, etc.).
- **Prompt:**
```
I want the project to be [DESIGN DIRECTION].
Using @project-overview.md, @user-flow.md, and @tech-stack.md, create `design-rules.md` covering:
- Design principles and accessibility guardrails
- Color palette and typography
- Component styling conventions
- Spacing, layout, and interaction patterns
```

## Phase 3 — Project Rules

### Step 7 — Engineering Standards
- **Deliverable:** `llm/project-rules.md`
- **Focus:** directory map, file naming, code documentation, workflow standards.
- **Prompt:**
```
We are building an AI-first codebase that must stay modular, readable, and well documented. Files need descriptive headers, functions require JSDoc/TSDoc, and individual files should stay under 500 lines.
Using @tech-stack.md, @user-flow.md, @project-overview.md, and @design-rules.md, draft `project-rules.md` with:
- Directory structure and naming conventions
- Code organisation patterns and documentation rules
- Development workflow expectations
```

## Phase 4 — Delivery Planning

### Step 8 — Phased Roadmap
- **Deliverables:** `llm/phases/setup-phase.md`, `llm/phases/mvp-phase.md`, plus any follow-up phases.
- **Prompt:**
```
Create an iterative development plan from setup to MVP to advanced phases.
Rules:
- Setup = barebones but running
- MVP = core value delivered
- Later phases = enhancements, scale, polish
- Each phase goes in its own document with scope and 3–5 actionable steps per feature
- Plans must build on the previous phase and remain shippable

Use @project-overview.md, @user-flow.md, @tech-stack.md, and @project-rules.md for context.
Place the files in `llm/phases/`.
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

### Step 10 — README Refresh
- **Deliverable:** Updated project README.
- **Prompt:**
```
Using @project-overview.md, @user-flow.md, @tech-stack.md, and @project-rules.md, refresh the README with a concise project summary and key conventions.
```

### Step 11 — Documentation Audit
Confirm `llm/` contains the full set:
- `llm/project-overview.md`
- `llm/user-flow.md`
- `llm/tech-stack.md`
- `llm/design-rules.md`
- `llm/project-rules.md`
- `llm/phases/setup-phase.md`
- `llm/phases/mvp-phase.md`
- `llm/phases/[additional-phase].md`

### Step 12 — Kickoff Prompt
- **Deliverable:** First development task or pairing session.
- **Prompt:**
```
Let's get started on our project.
```
- **Attach:** Agent Rules, `setup-phase.md`, `tech-stack.md`, and `project-overview.md` to keep the assistant grounded.

## Tips for Success
- Iterate on earlier docs as new insights emerge.
- Ask clarifying questions instead of guessing requirements.
- Keep prompts and outputs in sync—update documentation when decisions change.
- Store everything in `llm/` so contributors and agents have a single source of truth.

## Directory Quick Reference
```
llm/
├── project-overview.md
├── user-flow.md
├── tech-stack.md
├── design-rules.md
├── project-rules.md
└── phases/
    ├── setup-phase.md
    ├── mvp-phase.md
    └── [additional-phase].md
```
