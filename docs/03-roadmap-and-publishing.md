# Roadmap, Tech Stack & App Store Path

## Tech stack (chosen for: no Mac, no coding experience, one codebase → many devices)
| Layer | Choice | Why |
|---|---|---|
| App | **Expo (React Native) + TypeScript** | iPhone, iPad, Android and web from one codebase |
| iOS builds | **EAS Build** (cloud) | Builds and submits iOS apps without owning a Mac |
| Widgets / Live Activities | Small Swift target via Expo config plugin | Apple requires native widget code |
| Local data | SQLite with an offline-first sync layer | Works with no signal |
| Backend | **Supabase** (Postgres, auth, row-level security, storage) | Multi-user/family/org sharing, attachments |
| AI | Server function calling Claude API; BYO-key option | Keeps the AI key safe; personalization |
| Calendars | Google / Microsoft Graph / Apple EventKit | Read-only first |
| Web / desktop / fridge | Expo web build | Smart-fridge screens run browsers |

## What you need
- An **iPhone** (and ideally an iPad) for testing via TestFlight.
- **Apple Developer Program** — $99/yr. For a commercial product, enroll as an **organization**
  (needs an LLC + free D-U-N-S number, allow 1–3 weeks).
- **Google Play** — $25 one-time (Phase 5).
- Accounts: Expo, Supabase, Anthropic (Claude API), GitHub (have it).
- Monthly costs at start: ~$0–25 (free tiers) + AI usage.

## Phases
| # | Phase | Contents | You get |
|---|---|---|---|
| 0 | **Prototype** | Clickable web prototype: week/today board, cards, pie timer, step check celebration, shake cue, focus fade | Feel it on your phone before code |
| 1 | **MVP — personal** | Tasks, steps, cadences, done-when + proof, notes, attachments, scheduling engine, rollover/escalation, focus mode, celebrations, offline, settings | Daily-use app via TestFlight |
| 2 | **AI + Calendar** | AI estimates that learn, AI steps, templates, goal coach + evidence cards, calendar sync, meeting prep, widgets | Smart planner |
| 3 | **Process tools** | People & contact log, blocked/waiting steps, follow-up cadences, bottleneck insights | Your work follow-up flow |
| 4 | **Inbox + Feel** | Email-to-task (Gmail/Outlook), share-sheet for texts, themes, shake/escalation polish, milestones | Dream features begin |
| 5 | **Family + platforms** | Family workspace, family display mode (tablet/fridge web), Android | Public launch candidate |
| 6 | **Teams** | Org workspaces, nested goal trees across people, hand-offs, shared SOP library, proof unblocking, CRM | B2B product |

**App Store launch** recommended at end of Phase 2 (or 3) with a subscription for AI features.

## Publishing checklist (summary — expanded when we get there)
1. LLC + D-U-N-S → Apple Developer (organization).
2. App name & bundle ID reserved in App Store Connect; trademark search on the name.
3. Privacy policy + terms (hosted page); App Privacy "nutrition label".
4. Sign in with Apple (required if offering other social logins).
5. In-App Purchase setup: subscription (AI) + one-time BYO-AI unlock.
6. Screenshots for 6.9" iPhone and 13" iPad; app preview video.
7. TestFlight beta (internal → external testers).
8. App Review: avoid medical/treatment claims; explain calendar/email permissions clearly.
9. Launch, then iterate on analytics + user interviews.
