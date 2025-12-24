# Repository Guidelines

## Project Structure & Module Organization
- `README.md` describes the boilerplate purpose and how to start.
- `llm/` is the source of truth for documentation-first planning:
  - `llm/project/` holds the canonical project definition, rules, and phased plans.
  - `llm/context/` stores focused reference notes (specs, models, usage patterns).
  - `llm/workflows/` contains repeatable runbooks (e.g., local dev setup).
- `LICENSE` defines licensing terms.

## Build, Test, and Development Commands
This repo is documentation-first; it does not ship runnable code by default. The standard commands you should mirror in downstream projects are documented in `llm/workflows/dev-env-local.md`:
- `npm install` — install dependencies.
- `npm run dev` — start the local dev server with hot reload.
- `npm run lint` — lint (use `-- --fix` to auto-fix).
- `npm run build` — type check and build for production.
- `npm run test` — run tests (optionally with `-- --coverage`).

## Coding Style & Naming Conventions
- Use kebab-case for doc filenames (e.g., `user-flow.md`).
- Start each doc with a one-line purpose statement.
- Keep docs short and linkable; prefer multiple small files to one large file.
- Follow any project-specific standards documented in `llm/project/project-rules.md` once created.

## Testing Guidelines
- No automated tests live in this boilerplate yet.
- For projects that add tests, document the framework and coverage target in `llm/project/tech-stack.md` and align with the workflow in `llm/workflows/dev-env-local.md`.
- Use consistent naming like `*.spec.ts` or `*.test.ts` once a framework is chosen.

## Commit & Pull Request Guidelines
- Commit history uses short, descriptive, plain-English messages (no strict conventional-commit format).
- Prefer imperative mood and scope clarity (e.g., “add project overview example”).
- Pull requests should include a concise summary, list of doc updates, and any follow-up tasks.
- If you introduce new workflows or rules, update `llm/README.md` and the relevant file in `llm/project/`.

## Documentation Workflow
- Start with `llm/project/setup.md` to generate the baseline docs.
- Copy `llm/project/project-overview-example.md` to `llm/project/project-overview.md` and tailor it.
- Keep `llm/` as the canonical source of truth; code should follow the docs, not the other way around.
