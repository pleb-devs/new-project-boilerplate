# Repository Guidelines

## Project Structure & Module Organization
Treat `llm/` as the source of truth. Keep `llm/project/project-overview.md`, `llm/project/project-rules.md`, and `llm/project/phases/` current before touching code. Use `llm/context/` for focused implementation references (e.g., protocol notes) and `llm/workflows/` for repeatable runbooks (e.g., local dev setup). Runtime logic lives under `src/` with feature folders such as `src/auth/` or `src/dashboard/`; mirror that hierarchy in `tests/` (e.g., `tests/auth/login.test.ts`). Shared assets live in `public/` or `llm/assets/`. Begin every file with a one-line purpose note, cap it at 500 lines, and use descriptive kebab-case filenames like `src/editor/note-toolbar.tsx`.

## Build, Test, and Development Commands
Standardize on Node 20+. After `npm install`, rely on scripts: `npm run dev` for hot-reload development, `npm run build` for the production bundle and type checks, `npm run lint` or `npm run lint -- --fix` for formatting, and `npm run test` / `npm run test -- --coverage` for automated suites. Document extra tooling in `llm/project/project-rules.md` so future agents inherit the workflow. See `llm/workflows/` for common runbooks.

## Coding Style & Naming Conventions
Use TypeScript with 2-space indentation, single quotes, and trailing commas. Prefer pure functions declared with the `function` keyword, avoid classes and enums, and keep conditionals lean with early returns. Exported symbols need concise block comments; shared utilities belong in `src/lib/`. Use camelCase for variables (`isLoading`, `hasError`) and keep files in kebab-case inside the feature folder.

## Testing Guidelines
Default to Vitest + Testing Library. Name suites to mirror `src/`, such as `tests/dashboard/filters.test.ts`. Target at least 80% branch coverage; run `npm run test -- --coverage` before merges and record deltas in the relevant `llm/project/phases/` doc. Stub Nostr relay traffic in fixtures so tests stay deterministic and fast.

## Commit & Pull Request Guidelines
Write imperative commit subjects ≤60 characters (`Add setup guide`). Keep related changes together and commit documentation alongside code. PRs need a summary, linked issues or docs, verification commands, and screenshots or logs for UX changes. After rebasing, rerun build, lint, and coverage suites; flag any skipped step with rationale.

## Security & Configuration Tips
Store secrets (API keys, relay credentials) in `.env.local`; never commit them. List required env vars in `README.md`. Validate relay URLs and sanitize note payloads before persistence. Review dependency bumps with `npm audit` prior to shipping.

## Agent & Collaboration Notes
Review the latest `llm/` docs—especially `llm/project/`—before generating code and capture new decisions immediately. Cross-check open questions in `llm/project/phases/` before acting. When agents change code, update the affected planning doc in the same change set and log follow-up tasks in `llm/project/phases/`. Use `llm/context/` for implementation references you’ll cite during prompts and add/maintain repeatable runbooks in `llm/workflows/`. Ask clarifying questions instead of guessing.
