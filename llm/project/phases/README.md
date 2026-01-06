Purpose: Explain how to use the phases directory and the phase templates.

# Phases README

This folder contains the phased roadmap. Each phase is a short, shippable plan that builds on the last one.

## How to use
- Draft new phases from `phase-template.md`.
- Update `setup-phase.md` and `mvp-phase.md` in place, then add optional follow-up phases.
- Keep each phase tight: 3-5 actionable steps per feature.

## Protocol or crypto work
- Add a spec summary in `llm/context/` before implementation.
- Write tests first using spec-based fixtures or vectors.
- Verify the implementation by running those tests and document outcomes.

## Files in this folder
- `phase-template.md` (scaffold)
- `setup-phase.md`
- `mvp-phase.md`
- `review-and-hardening-phase.md` (optional)
- `[additional-phase].md` (optional)
