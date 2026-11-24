# Market, Integration & Research Notes

Researched Nov 2026. Prices and requirements change often, so check vendor pages before relying on numbers.
Evidence levels: **Strong** (meta-analysis / RCT) · **Some** (single trial or observational) · **Practitioner** (no controlled research).

---

## 1. What market research I can do well (and what needs you)

**I can do well:** desk research on competitors (App Store listings, pricing pages, review sites, help docs),
feature matrices, mining public reviews for recurring complaints, summarizing research papers, and checking
platform rules (Apple, Google, Microsoft) for integrations.

**Needs people:** actually using each app for a week, interviewing users, surveys, and real market sizing.
Highest-value next step: **talk to 8–10 people with ADHD** (half work-focused, half home-focused) using the
prototype, plus read the 1–2 star reviews of Tiimo, Structured, Sunsama and Motion to find unmet needs.

---

## 2. Competitor snapshot

| App | Core idea | Notable features | Price (approx.) | Takeaway for Cueue |
|---|---|---|---|---|
| **Tiimo** | Visual, neurodivergent-first planner | AI co-planner from typed or spoken input, visual focus timer, color-coded day; iPhone App of the Year 2025 | Free tier; Pro ~$42/yr–$10/mo | Closest competitor. One review says its routine notifications often fail, so reliable alerts are an opening |
| **Structured** | Timeline day planner | Simple visual timeline | ~$30/yr or ~$100 lifetime | A lifetime option is popular; consider it alongside the BYO-AI purchase |
| **Sunsama** | Guided daily planning | Morning planning ritual + **end-of-day shutdown ritual**, pulls tasks from other tools, time blocks | ~$16–22/mo, no free plan | Add a "Shut down my day" ritual next to "Start my day" |
| **Motion** | AI auto-scheduler | Schedules everything automatically; Google/Outlook/Apple calendars; now docs and workflows too | ~$19–34+/mo | Reviewers warn it **overschedules**. Our "doesn't fit" warning and pushing tasks to later days are a differentiator |
| **Reclaim** | Sits on top of your calendar | Protects habits and focus blocks by writing them to the calendar | ~$10–15/mo | Write focus and routine blocks back to the calendar (later phase) |
| **Akiflow** | Universal inbox | One inbox for tasks from email, Slack and more; command bar; AI by chat/voice | ~$19–34/mo | An **Inbox lane** for captured items before they're planned |
| **Amazing Marvin** | Very customizable | Toggleable "strategies", Pomodoro, ADHD-minded | subscription | Optional features you switch on, so the app stays simple by default |
| **Goblin Tools** | Free AI helpers | Task breakdown with a **"spiciness" slider** for how detailed the steps are; time estimates; tone rewriter/judge | free / tiny | Add a detail slider to AI steps; AI-drafted follow-up messages with a tone choice |
| **Llama Life** | One task at a time | Single-focus countdown list | subscription | A "Just this" focus mode that hides everything but the current task |
| **Todoist** | General task manager | **Forward an email to a project address to create a task** | paid tiers | The cheapest way to start email-to-task (see §4) |

**What nobody combines:** an ADHD-first personal planner **plus** team flows with hand-offs, proof of done,
fair recognition and manager review. That's Cueue's clearest position.

---

## 3. Feature ideas inspired by competitors (prioritized)

1. **Brain dump → plan:** type or speak a messy list; AI turns it into tasks with steps, estimates and suggested days (Tiimo, Akiflow).
2. **Inbox lane:** everything captured (forwarded emails, shared texts, quick adds) lands in an Inbox to sort in under a minute (Akiflow, Sunsama).
3. **Shut down my day:** an evening ritual that reviews what got done, celebrates, moves leftovers on purpose, and previews tomorrow (Sunsama).
4. **Step detail slider:** "fewer, bigger steps" ↔ "tiny steps" when AI breaks a task down, tied to energy level (Goblin Tools).
5. **AI follow-up drafts:** for Contact steps, draft the email or text with a tone choice (friendly / firm / formal) (Goblin Tools Formalizer).
6. **"Just this" focus mode:** full screen, one task, one next step, pie timer (Llama Life).
7. **Write focus blocks to calendars** so coworkers see protected time (Reclaim). Phase 3+.
8. **Desktop command bar and keyboard shortcuts** for fast capture (Akiflow).
9. **Rock-solid notifications:** Live Activities, lock-screen timer, alerts that repeat until acknowledged (a common complaint about competitors).
10. **Lifetime purchase option** in pricing tests (Structured).

---

## 4. Preparing for email and calendar integrations

### Calendars (read first, write later)
- **Google Calendar:** reading events is a *sensitive* scope. Verification typically takes **3–5 business days**
  and needs a written reason for each scope plus a demo video. Request the narrowest scope that works.
  Workspace admins can block untrusted apps.
- **Microsoft 365 / Outlook (Graph):** delegated `Calendars.Read` (and `Calendars.ReadWrite` later). Become a
  **verified publisher** (needs a Microsoft Partner Network account). Some company tenants require **admin
  consent**, which matters for team sales: plan an "ask your IT admin" flow.
- **Apple Calendar (EventKit, on device):** iOS 17+ has *write-only* and *full* access. Reading events needs
  full access with a clear usage message; adding prep blocks only needs write-only.

### Email (staged, to avoid big costs early)
- **Gmail:** reading mail uses *restricted* scopes. If the data passes through our server, Google requires a
  third-party **CASA security assessment, renewed every year**. One vendor estimated **$15k–$75k+** (unverified,
  may be dated).
- **Plan:**
  1. **Forwarding address** (like Todoist): each user gets `you@in.cueue.app`; forwarded emails become tasks
     with the source attached. No OAuth and no assessment. Works with any email provider.
  2. **iOS share sheet:** share an email or text to Cueue to create a task. iOS doesn't let apps read SMS, so this is the path for texts.
  3. **Outlook via Microsoft Graph** (`Mail.Read`, delegated) for work users.
  4. **Direct Gmail reading** once revenue justifies the yearly assessment. An aggregator like **Nylas**
     (priced per connected account) can speed up building, but confirm whether it changes the assessment requirement.
- **Prep checklist:**
  - privacy policy and support site on our own domain
  - Google Cloud project and Microsoft Entra app registration
  - scope list with reasons
  - demo videos
  - encrypted token storage
  - process email content without keeping it, and delete data when an account is disconnected
  - a clear data-use page users can read

---

## 5. ADHD research that suggests design and style changes

| Finding | Evidence | Design change |
|---|---|---|
| A 2025 study of a real-world adult ADHD app (12,000 users) found **navigation difficulty and clinical, "pathologising" language** were barriers; users new to their diagnosis valued it most | Some (Internet Interventions, 2025) | Keep strengths-based, plain language (no "disorder" or "symptoms" in UI copy); simple navigation; gentle onboarding for the newly diagnosed |
| In a self-guided online program for adults with ADHD, **77% didn't finish**; reminders were tested to improve this | Some (2022) | Plan for drop-off: "welcome back" flows with no guilt, auto-tidy the board after time away, reminders that can be snoozed |
| W3C guidance for cognitive and learning disabilities: don't rely on memory, use familiar icons and words, clear steps, show where you are, offer undo | Guidance (W3C COGA) | Undo after every check-off or delete, consistent button placement, a reading-level check on copy, a comfortable/compact density setting |
| Gamification evidence for ADHD is **mixed and mostly in children**; adult gamified health apps look helpful overall | Some / mixed | Keep celebrations optional and adjustable; rotate rewards so they stay novel; never punish |
| **Body doubling** is popular, but controlled evidence is thin and some people do worse | Practitioner / thin | Offer an optional "focus room" (work alongside others) as an experiment, described honestly |
| Fixed **Pomodoro** breaks raised fatigue faster than self-chosen breaks in a 2025 student study; results on rigid breaks are mixed | Some (students, not ADHD) | Offer break styles: every N minutes (current), Flowtime (break proportional to focus time), or when I choose; keep break lock optional |
| Time perception, immediate rewards, if-then plans, habits taking ~66 days | Strong / some | Already in Cueue (see `02-adhd-research.md`) |

**Style choices to test:** calm default palette with color used only for meaning; at most one strong
animation at a time; a reduced-motion preset; optional dyslexia-friendly font; larger tap targets on phones.

---

## 6. Productivity methods Cueue can build in

| Method | Evidence | How it would show up |
|---|---|---|
| Time management overall | **Strong:** a meta-analysis of 158 studies found moderate links to performance and **stronger links to well-being** (Aeon et al., 2021) | Position Cueue as reducing stress, not only producing more |
| If-then planning (implementation intentions) | **Strong** (Gollwitzer & Sheeran 2006) | Add a "When/where" field to routines: "After my 9am coffee → follow-ups" |
| Temptation bundling | **Some:** +51% gym visits when audiobooks were saved for the gym, fading over time (Milkman et al., 2014) | "Pair it with…" field: a podcast or treat that only goes with a dreaded task |
| Time blocking / timeboxing | Practitioner | Already in the scheduler; add calendar write-back later |
| Eat the frog → fresh hours | Practitioner | Already in: Heavy tasks go in fresh hours |
| Eisenhower matrix (urgent vs important) | Limited | A 2×2 triage view for the Inbox lane |
| Two-minute rule | Practitioner | A "Quick wins" group for tasks of 5 minutes or less, batched between meetings |
| Kanban work-in-progress limits | Practitioner | Cap "in progress" at 1–3 tasks; Switch task already pauses the others |
| Pomodoro / Flowtime | Mixed (see §5) | Break style setting |
| Weekly review (GTD) | Practitioner | Sunday weekly review ritual: goals, waiting-on list, next week preview |
| Body doubling | Thin | Optional focus room experiment |

---

## 7. Recommended additions, in order
1. Inbox lane plus email forwarding address plus iOS share sheet (capture first, no costly scopes)
2. Brain dump → plan (voice or typing)
3. Shut down my day + Sunday weekly review rituals
4. Step detail slider and AI follow-up drafts with tone choice
5. "Just this" focus mode
6. "When/where" and "Pair it with…" fields on routines
7. Break styles (interval / Flowtime / when I choose)
8. Undo everywhere, density setting, plain-language copy pass

---

## Sources
- Competitor roundups: [Morgen](https://www.morgen.so/blog-posts/adhd-productivity-apps), [Saner](https://www.saner.ai/blogs/best-adhd-planners), [BrightMind](https://brightmind.club/blog/adhd-planner-apps), [TilTaken](https://www.tiltaken.com/articles/adhd-planner-apps-honest-review)
- [Tiimo App Store](https://apps.apple.com/app/tiimo/id1480220328), [Tiimo product](https://tiimoapp.com/product)
- [Motion vs Reclaim (Morgen)](https://morgen.so/blog-posts/motion-vs-reclaim), [Reclaim comparison](https://reclaim.ai/blog/motion-vs-reclaim)
- [Sunsama daily planning & shutdown](https://www.sunsama.com/features/daily-planning-and-shutdown), [Sunsama vs Akiflow](https://morgen.so/blog-posts/sunsama-vs-akiflow), [Amazing Marvin vs Sunsama](https://akiflow.com/blog/amazing-marvin-vs-sunsama)
- [Goblin Tools Magic ToDo (Warwick)](https://warwick.ac.uk/services/library/using/productivity-tools/magic-todo-gobin-tools), [Goblin Tools App Store](https://apps.apple.com/us/app/id6739871366)
- [Todoist: forward emails](https://www.todoist.com/help/articles/forward-emails-to-todoist-JPJ1V339)
- Google: [Sensitive scope verification](https://developers.google.com/identity/protocols/oauth2/production-readiness/sensitive-scope-verification), [Restricted scope verification](https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification), [Security assessment](https://support.google.com/cloud/answer/13465431), [GMass cost estimate](https://www.gmass.co/blog/?p=9167)
- Microsoft: [Graph permissions overview](https://learn.microsoft.com/et-ee/graph/permissions-overview), [Nylas Microsoft scopes guide](https://developer.nylas.com/docs/cookbook/use-cases/build/microsoft-oauth-scopes.md)
- Apple: [TN3152 calendar access levels](https://developer.apple.com/documentation/technotes/tn3152-migrating-to-the-latest-calendar-access-levels.md), [Accessing the event store](https://developer.apple.com/documentation/eventkit/accessing-the-event-store.md)
- [Nylas pricing](https://nylas.com/pricing/)
- ["A one-stop shop": adult ADHD app study (2025)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC11847728/), [SMS reminders and adherence (2022)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9149073/), [Inflow feasibility](https://journals.plos.org/digitalhealth/article?id=10.1371%2Fjournal.pdig.0000083)
- [W3C: Making Content Usable for People with Cognitive and Learning Disabilities](https://www.w3.org/TR/coga-usable)
- [Gamified interventions for adults (scoping review)](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC10763397/), [ADHD serious games review (2025)](https://www.frontiersin.org/journals/psychiatry/articles/10.3389/fpsyt.2025.1605744/full)
- Body doubling: [arXiv 2509.12153](https://arxiv.org/html/2509.12153v1), [Popular Science](https://www.popsci.com/health/body-doubling-focus-benefits/)
- Breaks: [Self-regulated vs Pomodoro vs Flowtime (2025)](https://www.mdpi.com/2076-328X/15/7/861)
- [Temptation bundling, Milkman et al. 2014](https://pubmed.ncbi.nlm.nih.gov/25843979/)
- [Does time management work? Aeon et al. 2021](https://econpapers.repec.org/RePEc:plo:pone00:0245066)
