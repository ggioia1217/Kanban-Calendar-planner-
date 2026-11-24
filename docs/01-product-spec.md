# Product Spec — ADHD Kanban Week Planner (working title)

Status: **Draft v1** · Last updated: 2026-11-24
Owner: product owner (you) · Drafted with Claude

> One sentence: a weekly Kanban board where each day is a column, tasks are broken into steps that
> follow a process to a clear definition of "done", and an AI scheduler plans each day around your
> energy, your calendar and your deadlines — with a dopamine hit for every bit of progress.

---

## 1. Core principles (the "why" behind every feature)

These come from the research summary in [`02-adhd-research.md`](02-adhd-research.md).

1. **Make time visible.** ADHD involves measurable time-perception differences. Show time as a
   shape (filling pie timer), not a number.
2. **Help at the point of performance.** Cues, next steps and reminders appear *where and when* the
   work happens: the card, the widget, the lock screen.
3. **Always show the next step.** A goal is overwhelming; the next step is doable.
4. **Reward immediately and often.** Every checked step gives a reward, not only finished tasks.
5. **Plan with energy, not just with time.** Heavy tasks go in your fresh window.
6. **Forgive.** Missed days roll forward without shame. Streaks are forgiving.
7. **Adjustable sensory load.** Motion, sound, haptics and timers can all be turned down or off.

---

## 2. Object model (how things nest)

```
Workspace (Personal · Family · Organization)
 └─ Goal  (can contain sub-goals, unlimited depth)
     └─ Goal …
         └─ Task  (a card on the board)
             └─ Step  (checklist item)
```

### 2.1 Goal
- Title, description, "why it matters" (motivation note), target date (optional).
- **Unlimited nesting**: Goal → sub-goal → sub-sub-goal… The UI shows a breadcrumb trail
  (e.g. `Onboard Nurse J. › Credentialing › Background check`) and a progress ring that rolls up
  from children.
- Owner (person) and, in an organization, a team/department.
- Can **spawn routine tasks** (e.g. a goal "Run a 5K" spawns "Run 20 min, Mon/Wed/Fri").
- Optional **evidence card**: the research behind the routine, with links to the sources (AI-generated, must cite
  real sources; see §8.4).

### 2.2 Task (the card)
| Field | Notes |
|---|---|
| Title | The "goal" text on the card |
| Parent goal | Optional; shown as a breadcrumb in details |
| Context tag | Work / Home / custom (used by Focus Mode) |
| Schedule type | **One-off** (due date, optional due time) or **Routine** (cadence) |
| Cadence | Daily · Weekdays · Weekly on chosen days · Every N days · Monthly · **N days after last completion** |
| Difficulty | **Light · Medium · Heavy** — mental load; decides *when* in the day it goes |
| Span *(name TBD)* | Typical length band; gives the default estimate (see §2.4) |
| Priority | Low · Medium · High · Urgent |
| Estimate | User-entered **or** AI-estimated (only if user didn't enter one); always editable |
| Split mode | One block **or** chunked across the day/days (user choice per task) |
| Done when… | Definition of done (AI suggested, user editable) |
| Proof | Required by default; resolution note + optional attachment(s) |
| Notes | Free text; first line shows on the card |
| Attachments | Photos, files, links, forwarded emails |
| Source | Manual · Template · Email · Text (share sheet) · Calendar · Assigned by coworker |
| Related person(s) | Links to People (§2.6) |
| Status | Not started · In progress · **Blocked / Waiting** · Done |

### 2.3 Step (checklist)
- Text, order, checked/unchecked, **checked-at timestamp** (recorded automatically — no per-step
  time estimates; we learn where processes slow down from timestamps instead).
- **Step types:**
  - *Plain* — just check it off.
  - *Contact* — "Reach out to {person}". Checking it logs the contact with the date/time/channel to the person's
    history.
  - *Waiting on* — puts the task into **Blocked/Waiting**, records who/what it's waiting on, and
    auto-schedules follow-up nudges on a cadence until resolved. (Later: an email reply or a
    coworker's proof can resolve it automatically.)
  - *Proof* — requires an attachment or note to check off.
- Steps come from: **AI** (generated from title + done-when), a **template** (preset steps), or
  the user.

### 2.4 Difficulty vs. Span (two separate dials)
Difficulty = *how hard it is on the brain*. Span = *how long it usually takes*. A hard phone call
can be 10 minutes; easy data entry can be 3 hours.

Default **Span** bands (customizable per user):

| Span | Default estimate | Behavior |
|---|---|---|
| Quick | 15 min | Good filler between meetings |
| Short | 30 min | |
| Standard | 1 hr | |
| Long | 2 hr | Suggest a break midway |
| Marathon | 4 hr + | Auto-offers splitting into chunks |

> Naming: you didn't like "Size". Working name is **Span**; alternatives to test: *Time Block*,
> *Stretch*, *Length*, *Effort*. Final name decided in user testing.

### 2.5 Templates & Task Library
- A template = title pattern + steps + done-when + default difficulty/span + proof rules.
- Personal library to start. **Organizations** get a shared library that works as living SOPs
  (e.g. "Nurse onboarding", "Missing-time billing correction").
- A template can include **hand-offs** (step N assigned to a role/department) — Phase 6.

### 2.6 People (contacts)
- Name, organization, channel(s) (phone/email), owner (who manages this relationship).
- Timeline: every contact step logged against them, open requests, average response time.
- Later: CRM sync decides ownership/assignment automatically.

---

## 3. The board (screens)

### 3.1 Orientation
- **Landscape:** full week, 7 day columns (start day configurable).
- **Portrait:** Today only, as a vertical ordered list; swipe left/right for adjacent days.
- iPad: week view in both orientations when width allows.

### 3.2 Day column
- Calendar events appear as fixed, non-draggable blocks (grey), with an auto **Prep** card before
  meetings.
- Tasks appear in scheduled order. Default display = **ordered list** with soft times;
  optional **timeline mode** (exact slots) for users who prefer it.
- Work hours band shown; breaks shown as small cards (water, walk, stretch, yoga).

### 3.3 Card (main view) — minimal on purpose
```
┌───────────────────────────────┐
│ Follow up: Acme vendor record │  ← title (goal)
│ → Call Dana re: missing time  │  ← NEXT unchecked step
│ ◔  📅 Thu  🔁  ✉️              │  ← pie timer · due · repeat · source icon
└───────────────────────────────┘
```
- **No time estimate number on the card** (time blindness) — instead a **small pie timer**:
  estimate = 100%, fills red as time is spent. Toggle off in settings (anxiety option).
- Progress shown subtly by step dots or a thin bar.
- Blocked/Waiting cards show a ⏸ badge and who they're waiting on.
- Source icon only when not manually created.

### 3.4 Current task ("Now" mode)
- The card in progress expands: big pie timer, the next step, notes, a "done for now / switch"
  control.
- At **1× estimate**: gentle check-in ("Still on this? +15 min / Done / Switch").
- At **2× estimate**: the day re-plans (see §4).

### 3.5 Task details (tap a card)
Full step list, notes, attachments, done-when, proof, source (e.g. original email), people,
contact log, goal breadcrumb, history (times rolled over, time spent vs estimate).

### 3.6 Focus Mode (work)
- Enter a **work schedule** (e.g. Mon–Fri 9–5).
- During work hours, non-work cards are faded (high transparency) and become **gradually
  more opaque** as the end of the workday approaches, helping the transition home.
- Manual "Focus: Work / Home / All" switch anytime.

### 3.7 Widgets (iOS, later Android)
- Small: **Next up** — title + next step + pie timer; tap to check the step (with a mini celebration).
- Medium/Large: next 3–5 items, today's progress ring.
- Lock-screen widget / Live Activity for the current task's timer.

---

## 4. The scheduling engine

### 4.1 Inputs
Calendar events · work hours · fresh window · task due dates / cadences · priority · difficulty ·
estimates · breaks preferences · pinned items · current progress.

### 4.2 Placement rules (in order)
1. Fixed calendar events and their **prep blocks** are placed first.
2. **Pinned** items (user dragged them) stay where put.
3. **Heavy** tasks go into the **fresh window** (default from onboarding, e.g. 9am–1pm; optional
   medication-timing offset).
4. Remaining tasks ordered by an **urgency score**:
   `due-date proximity` → `priority` → `escalation (missed routines)` → `difficulty fit for time of day`.
5. **Light + Low priority** fill the end of the day and slide up as earlier tasks finish.
6. Buffers (5–10 min) between tasks; a break suggestion every ~90 min (configurable).
7. Long tasks are chunked if split mode is on (variety keeps the brain engaged).

### 4.3 When the plan changes (event-driven, not clock-driven)
Re-plan triggers:
- Task added / edited / completed / deleted
- A calendar event is added, moved or removed
- Day start ("Plan my day")
- Current task reaches **2× estimate**

Never moved by a re-plan: the **current task** and **pinned** items. Today re-flows automatically;
changes to **future days** are proposed and accepted with one tap.

### 4.4 Overbooked days
- A warning appears on the day plan.
- Tasks with **later due dates** move first, ordered by how far away the due date is.
- Nothing is crammed silently.

### 4.5 Rollover & escalation
- Unfinished tasks roll to the next day automatically (done steps stay done).
- **Missed routines escalate**: urgency +1 per missed day, with stronger cues (see §6.2).
- After **3+ rollovers**, a kind prompt appears: *Break it down · Delegate · Reschedule · Drop it*.
  Rollover tuning will be revisited after real use.

### 4.6 Learning
- Actual time vs estimate is recorded per task/template; routine estimates converge on reality.
- The fresh window adjusts based on when Heavy tasks are actually finished fastest (suggested, not forced).
- Step timestamps reveal process bottlenecks (e.g. "vendor fixes wait ~4 days at step 2").

---

## 5. Calendar integration & meeting prep
- Read-only sync: Google, Microsoft 365/Outlook, Apple (iCloud) calendars.
- For meetings with attendees, an automatic **Prep** card (default 15 min, before the meeting) is
  created. It can be turned off per meeting or globally.
- Prep card contents (AI):
  - Summary of the **meeting description**
  - Related tasks/notes/contact history found in the planner (matching people, companies, keywords)
  - Suggested questions/agenda and "bring this" items
- Prep starts appearing early (e.g. the day before) so preparation can begin ahead of time.

---

## 6. Feedback: dopamine & cues

### 6.1 Rewards
- **Every step checked**: micro-animation + haptic + optional sound.
- **Task done**: bigger celebration (confetti/theme-specific).
- **Milestones** per routine/template: 10, 25, 50, 100, 250… completions, with the next milestone
  always visible ("7 more to your 25th follow-up!").
- **Forgiving streaks**: e.g. 5 of 7 days keeps a streak alive.
- Daily/weekly recap: "You moved 14 steps forward this week."

### 6.2 Attention & urgency cues (escalating, all adjustable)
| Level | Trigger examples | Visual | Haptic | Audio |
|---|---|---|---|---|
| 1 | Due tomorrow; routine missed once | Soft glow | — | — |
| 2 | Due today; current task near estimate | Gentle card **shake** | Light tap | Optional chime |
| 3 | Overdue; routine missed 2–3 days; 1× estimate reached | Stronger shake + color | Double tap | Optional tone |
| 4 | Badly overdue / 2× estimate | Board-level shake of that card | Pattern | Optional |
- Global intensity slider; respects iOS **Reduce Motion**; quiet hours; per-cue toggles.

### 6.3 Wellness breaks
Water, walk, stretch, short yoga (≤15 min) suggestions, with optional links to short guided videos.

---

## 7. Definition of done & proof
- Every task has **Done when…** (AI-suggested from title/template; e.g. "Signed service agreement
  received").
- Completing a task asks for a **resolution note** ("Nurse confirmed hours; screenshot of
  timekeeping attached") and **proof** (required by default; can be set to optional per task/template).
- Proof travels: in organizations, proof attached to one person's task can **unblock** a coworker's
  waiting task.
- AI learns typical "done" patterns per template to suggest better done-when text and proof.

---

## 8. AI features
1. **Time estimates** — only when the user leaves it blank; always editable; learns from actuals.
2. **Step generation** — from title + done-when, or adapted from a template.
3. **Day planning** — the engine is rule-based (reliable, works offline); AI assists with estimates,
   difficulty guesses, and explanations ("why is this at 9am?").
4. **Goal coach** — conversation about a personal goal → proposes routines, cadence, steps,
   milestones, and an **evidence card** with real citations (no invented sources; if evidence is
   weak, say so).
5. **Meeting prep** — summaries and related context (§5).
6. **Inbox-to-task** (Phase 4) — email first (Gmail/Outlook); texts via iOS share sheet (iOS doesn't let apps read
   SMS directly). Card shows the source; details link to the original.

**Offline:** board, tasks, steps, scheduling and rewards all work offline; AI features queue until
online. **Bring-your-own-AI:** a one-time purchase unlocks using your own AI provider key.

---

## 9. Workspaces, sharing & organizations
- **Personal** (default) — one unified board, filterable by context.
- **Family** (Phase 5) — individual planners grouped into a family view; shared chores/routines;
  big-screen **family display mode** for tablets and smart-fridge screens (web app).
- **Organization** (Phase 6):
  - Goal trees spanning people and departments.
  - Assign/hand-off tasks; templates with role-based steps (SOPs).
  - Proof-based unblocking between coworkers.
  - Goals that spawn routine tasks for others.
  - CRM integration: contact ownership → automatic assignment.
- Built **multi-user from day one** in the data model, even though the UI comes later.

---

## 10. Settings worth having from v1
Week start day · work schedule · fresh window (+ medication offset) · list vs timeline · buffers &
breaks · cue intensity / sounds / haptics / reduce motion · pie timer on/off · rollover prompt
threshold · Span bands · default proof rule.

---

## 11. Out of scope for now
Themes/personality per board (planned Phase 4 visual pass) · two-way calendar write-back ·
CRM · Android/desktop native apps (web covers desktop first).

---

## 12. Additions from prototype reviews (Nov 2026)

### 12.1 Time horizons
- **Goals** use days / weeks / months (e.g. "Lose 15 pounds · 3 months"). Sub-goals can have their own,
  shorter horizon.
- **Tasks and routines** use minutes / hours (e.g. "Log meals · 10 min · daily", "Exercise · 1 hr · 3× a week",
  "Weigh-in · 5 min · weekly").
- Goal card: progress ring, "Day X of Y", end date, and a bar comparing progress to time passed
  ("On pace" / "A little behind. Today's routines catch you up").
- Routine progress = completions ÷ expected completions over the goal's horizon, so daily practice
  visibly builds the long-term goal.

### 12.2 Template library & workflows
- **Company processes**: stages owned by roles (Recruiter, Credentialing, HR, Payroll, AR, Vendor, You).
- **My templates**: saved from any goal ("Save as template").
- Shown as a **swimlane flow**: one lane per person/team, stages left to right, dashed arrows for hand-offs.
- Using a process creates the goal tree. Your stages land on your board; a stage that follows someone
  else's waits ("Waiting on HR: Background check") and unblocks automatically when that stage completes.
- Phase 6 makes this real across coworkers (assignment, notifications, proof hand-off, CRM ownership).

### 12.3 Card interaction
- Cards show the next step as a checkbox; checking it advances to the following step.
- When every step is checked, a **Complete** button appears to verify the task is done (resolution + proof).

### 12.4 Edge light
- Every visible card has a light that runs along its top edge, peaking at the center and fading out on the right.
- Urgency changes color (accent → amber → red), speed (9s → 1.6s) and thickness/glow.

### 12.5 Flow builder, hand-offs and permissions
- The swimlane diagram is also the editor: "+ Add stage" in any lane, arrows to reorder or change lanes,
  a stage panel for name, owner and tasks (pulled from template tasks or written new).
- A stage finishing triggers the next stage's tasks for its owner. The person finishing can add a task for the next owner.
- **Job levels**: Admin · Manager · Team lead · Member, set in an org chart.
  - Company flows: created by anyone who manages people; structure (order, owners, hand-offs) changed by the
    flow owner or an admin.
  - Department leads edit the tasks inside their own stages.
  - Members use flows and can save personal copies; admins and leads track progress.
- **CRM**: supplies contacts and owners; an "Account owner (CRM)" lane resolves to that owner when a flow starts.

### 12.6 Day flow additions
- Switch task: pick another task; the current one pauses and keeps its time.
- Get ahead: when today is clear, pull in tasks due later; finishing early has its own celebration.
- Notifications sit at the top of the screen, at most two at a time.
