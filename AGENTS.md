# Repository Guidelines

## Project Structure & Module Organization
Treat `llm/` as the single source of truth before writing code. Maintain current context in `llm/project-overview.md`, `llm/project-rules.md`, and `llm/phases/` so future contributors and agents stay aligned. When implementation begins, keep runtime logic in `src/`, mirror specs under `tests/`, and place reusable assets in `public/` or `llm/assets/`. Each file should include a brief purpose note at the top, stay under 500 lines, and live inside a feature folder such as `src/auth/` or `src/dashboard/`.

## Build, Test, and Development Commands
Standardize on Node 20+. After initializing `package.json`, add and rely on the following scripts:
- `npm run dev` — launch the local app with hot reload.
- `npm run build` — create the production bundle and surface type errors.
- `npm run lint` — run ESLint/Prettier checks; use `npm run lint -- --fix` before committing.
- `npm run test` — execute the automated suite; add flags like `--coverage` when auditing metrics.
Document any extras (storybook, database seeds) in `llm/project-rules.md`.

## Coding Style & Naming Conventions
Write TypeScript with 2-space indentation, trailing commas, and single quotes. Prefer pure functions (`function handleSubmit() {}`) over classes, and choose descriptive camelCase variables. Exported symbols need concise block comments, and shared helpers belong in `src/lib/`. Use kebab-case filenames (`user-profile.tsx`) and keep conditionals lean with early returns.

## Testing Guidelines
Default to Vitest + Testing Library unless `llm/tech-stack.md` says otherwise. Structure tests to mirror `src/` (for example, `tests/auth/login.test.ts`). Require at least 80% branch coverage and run `npm run test -- --coverage` before merging. Capture the rationale for new or adjusted tests in the relevant document under `llm/phases/`.

## Commit & Pull Request Guidelines
Write short, imperative commit subjects (≤ 60 characters) such as `Add setup guide` or `Update README.md`. Group related changes per commit, note doc updates alongside code, and avoid drive-by edits. Pull requests must include a concise summary, linked issues or docs, verification steps (commands run), and screenshots or terminal snippets for UX changes. Re-run build, lint, and tests after rebasing to confirm nothing regressed.

## Agent & AI Collaboration
Share recent docs, open questions, and decision logs when prompting assistants. Record agent-driven decisions in the matching `llm/` doc to keep humans in the loop. When agents modify code, ensure accompanying documentation lands in the same change set to prevent drift between implementation and guidance.
