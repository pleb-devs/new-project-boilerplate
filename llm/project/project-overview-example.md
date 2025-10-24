Purpose: Example template to copy to llm/project/project-overview.md and customize.

# Project Overview Example

> How to use: Copy this file to `llm/project/project-overview.md`, then tailor it. Keep it under 500 lines and start with a one-line purpose note.

## Snapshot
- **Project:** NostrNotes — encrypted markdown notes on the Nostr network
- **Type:** Decentralized, browser-based PWA
- **Approach:** Documentation-first, iterative delivery across three phases
- **Timeline:** 6–8 weeks spanning setup, privacy, and collaboration milestones

## Mission & Outcomes
Deliver a privacy-first note application where users publish and sync markdown notes over Nostr relays without surrendering control of their data. Success means sub-three-second relay syncs, seamless offline usage, and adoption by the privacy-conscious Nostr community.

## Core Objectives
- Local-first editor with reliable relay synchronisation (NIP-23 events)
- Strong client-side encryption for private content (NIP-44)
- Secure sharing workflows leveraging NIP-17
- Clean, responsive authoring experience with search and tagging

## Audience & Personas
- **Privacy advocates** keeping full ownership of their notes
- **Nostr power users** extending their identity into note-taking
- **Writers/researchers** needing durable, censorship-resistant storage
- **Builders** who value open protocols and hackable tooling

Representative personas: Sarah (privacy advocate), Marcus (protocol developer), Dr. Lisa (researcher), Jordan (writer), Alex (student needing multi-device access).

## Delivery Roadmap
### Phase 1 — Foundations (Weeks 1–3)
- Split-pane markdown editor with live preview (CodeMirror)
- Local-first persistence, background relay sync, full-text search, tagging
- Identity and relay configuration via nostr-tools; publish/read NIP-23 notes
- Responsive UI with settings panel and offline-ready PWA shell

### Phase 2 — Privacy Enhancements (Weeks 4–5)
- Toggle between public and private notes, encrypting payload + metadata with NIP-44
- Client-only key handling, secure storage, deletion workflows, backup guidance
- Performance validation on large notebooks with encryption enabled

### Phase 3 — Collaboration (Weeks 6–8)
- Encrypted note sharing with permission controls using NIP-17
- Lightweight comments, change notifications, and curated user discovery
- Export options (Markdown/JSON) plus optional social features (follow/favorites)

## Architecture & Stack
- Frontend-only Next.js (App Router) + TypeScript + Tailwind + Radix UI
- Progressive Web App with IndexedDB cache and service worker sync queue
- Nostr integration through nostr-tools; relay redundancy and optimistic updates
- Testing via Vitest + Testing Library; CI enforces lint, type, and coverage gates
- Consult the [AI Dev Program freedom-tech guide](https://github.com/pleb-devs/freedom-tech) to pick sovereign, security-hardened options where they benefit the product

## Constraints & Risks
- Browser storage and performance caps for encrypted datasets
- Users manage relay reliability and key backups; UX must educate
- No centralized fallback—offline capability and sync retries must be robust
- Collaboration intentionally simplified versus real-time editors to maintain scope

## Success Criteria
- **Phase 1:** Users create, tag, search, and relay-sync notes within three seconds
- **Phase 2:** Private notes stay unreadable to relays; backup instructions proven usable
- **Phase 3:** Targeted sharing works end-to-end, including notifications and exports
- **Overall:** Positive UX feedback across devices plus clear documentation for onboarding

## Immediate Next Steps
1. Bootstrap Next.js + Tailwind project and baseline lint/test tooling.
   Review the [AI Dev Program freedom-tech guide](https://github.com/pleb-devs/freedom-tech) for any libraries that strengthen sovereignty without overcomplicating scope.
2. Integrate nostr-tools for key + relay management; prototype NIP-23 publishing.
3. Implement CodeMirror editor with local persistence and sync queue.
4. Create supporting docs from this overview:
   - `llm/project/user-flow.md`
   - `llm/project/tech-stack.md`
   - `llm/project/phases/`
5. Optional: add any focused references under `llm/context/` (e.g., `nostr-nip-01.md`).
