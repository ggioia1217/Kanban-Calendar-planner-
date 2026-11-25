# Decision Log & Open Questions

## Decided
| # | Decision |
|---|---|
| D1 | iPhone + iPad first; Android, web/desktop and smart-fridge (web) later |
| D2 | Personal use first, commercial product as the goal |
| D3 | Expo/React Native, cloud builds (no Mac), Supabase backend |
| D4 | One unified board + Focus Mode that fades non-work items, re-opaquing toward end of workday |
| D5 | Tasks can be one block or split into chunks (user choice) |
| D6 | No per-step time estimates; step timestamps recorded automatically; Blocked/Waiting step type |
| D7 | "Done when…" on every task; resolution note + proof **required by default** |
| D8 | Contacts/People list; expands to org-wide hand-offs and CRM later |
| D9 | Ordered list default, optional timeline mode |
| D10 | Fresh window user-set (default 9am–1pm), optional medication offset, learned suggestions |
| D11 | Event-driven re-planning; check-in at 1× estimate, re-plan at 2×; current & pinned never move |
| D12 | Overbooked → push later-due tasks first; missed routines escalate daily with visual/haptic/audio cues |
| D13 | Difficulty (Light/Med/Heavy) separate from Span (Quick→Marathon); name "Span" TBD |
| D14 | Card = title, next step, pie timer, due, repeat, source — no visible estimate number |
| D15 | Goals nest to unlimited depth |
| D16 | Calendar read-only; auto prep blocks (toggle per meeting/global) using meeting description + related tasks |
| D17 | Offline-capable; AI queues when offline |
| D18 | Subscription for AI; one-time purchase for bring-your-own-AI |
| D19 | Team/org features last (Phase 6), but data model multi-user from day one |
| D20 | Urgency cue = **edge light**: a glow travels each visible card's top edge left to right, brightest at the center, fading at the right; faster, thicker and redder as urgency rises (plus the periodic shake) |
| D21 | Card color = what it needs from you: Now (indigo), Due today (amber), Late (red), Break (green), Waiting (grey dashed); a dot still shows Work/Home |
| D22 | Breaks are timed items with options (water, bathroom, meditation, yoga, walk, social, reward); optional **break lock** pauses check-offs until a due break is taken |
| D23 | Breaks are suggested only after real effort: after **90 minutes of work** since the last break (adjustable in Profile), or a **reward break after a long task** (60+ minutes actually spent on it). Finishing a short task, even a heavy one, never triggers a break |
| D24 | Completed steps collapse behind a progress bar; completed items are viewable from the day's progress bar; steps can be unchecked and tasks reopened |
| D25 | Current task gets an expanded Now card (goal path, pie, done-when, next steps, notes, pause/break/switch) |
| D26 | "Start my day" mode: first task starts its timer; finishing a task auto-starts the next (toggle) |
| D27 | Goals view: unlimited nested sub-goals, progress rolls up from tasks, add tasks directly under any goal |
| D28 | No separate "check next step" button: step checkboxes only (also on the card itself). A **Complete** button appears once all steps are checked, to verify the task is done |
| D29 | Goals have time frames in **days / weeks / months**; routines and tasks inside use **minutes / hours**. Goal cards show progress vs. time passed and "Day X of Y" |
| D30 | Routine progress toward a goal = completions vs. how many times the routine should happen in the goal's time frame |
| D31 | "Suggest routines (AI)" breaks a long goal (e.g. weight loss) into routine sub-goals with small daily/weekly tasks |
| D32 | **Template library**: company processes (shared, role-owned stages) and personal templates (saved from any goal). Usable from Add task or the Library |
| D33 | Company processes render as a **swimlane flow** (lanes = people/teams, dashed arrows = hand-offs). Using one creates the goal tree; my stages go on my board, stages after a teammate's wait until that stage is done |
| D34 | "Switch task" opens a picker: choose another task; the current one pauses with its time saved and stays near the top |
| D35 | Notifications appear at the top of the screen, at most two at a time, and fade on their own |
| D36 | **Get ahead**: when today is clear, offer tasks due later; finishing a pulled-in task early gets its own celebration (rising sparkles, a longer chime, "N done early this week") |
| D37 | **Flow builder**: the swimlane diagram is the editor. Add stages per lane, reorder, move between lanes, set owners, and pull in template tasks or write new ones |
| D38 | Completing a stage automatically starts the next owner's tasks. When completing, you can add an extra task for the next owner |
| D39 | **Org chart and job levels** (Admin, Manager, Team lead, Member). Anyone who manages people can create company flows. The flow owner controls order, owners and hand-offs; departments edit the tasks in their own stages |
| D40 | **CRM**: contacts (candidates, vendors, clients) and their owners. An "Account owner (CRM)" lane assigns that stage to the contact's owner when a flow starts |
| D41 | Family flows use the same builder, with lanes for family members |
| D42 | **Branching flows**: one stage can start several stages at once (fan-out), and a stage can wait until all of its prerequisite stages are done (fan-in). Example: Offer approved starts Recruiting, Compliance, HR and Payroll in parallel; Orientation waits for all four |
| D43 | Flow diagram columns = how far along the chain a stage is, so parallel stages line up in the same column marked "in parallel" |
| D44 | Builder: "+ Next" on a stage, dashed boxes in every lane, and "When this is done, also start a stage for…" all add stages after the selected one. "Starts when these are done" sets what a stage waits for (loops are prevented) |
| D45 | Main page top bar trimmed to: Menu, Focus (All/Work/Home), Notifications bell, and a **+ New** dropdown (Task, Goal, Flow, From a template). Board view (Auto/Week/Today) moved to Settings |
| D46 | **Menu drawer** grouped as Plan (Today & week, My goals, Flows, Templates & ideas), Team (Notifications, Team activity, Org chart, CRM), Me (Achievements, Insights, Profile & my day), then Settings and Help. Every full-screen page has a menu button, Back and breadcrumbs |
| D47 | Phones get a slim bottom tab bar (Today, Goals, Flows, Inbox, Menu); it can be turned off in Settings |
| D48 | **My goals** has three tabs: I own, I'm part of (flows a coworker started), Waiting on others (with Request update and replies) |
| D49 | **Flows hub**: Active runs with progress and who holds each stage, Templates, Drafts, and Suggestions |
| D50 | **Full-screen flow builder**: drag a stage into another lane to change its owner; drag from a stage's handle onto another to connect them; click a line to edit the connection (starts when finished / same time / helpful but not required, wait time, what gets handed over, only-when condition, with suggestions) |
| D51 | **Flow suggestions**: anyone without flow rights can build a flow or suggest changes to an existing one; managers review, edit, approve or request changes with a note |
| D52 | ~~Team vs team leaderboard~~ replaced by D54 |
| D53 | **Templates & ideas**: ready-made home, family and work routines (morning launch, weekly reset, meals, bills, car, health, pets, school week, and more) with research notes where evidence exists |
| D54 | **Leaderboard = individuals within your own team.** Categories: effort points (each finished task weighted by difficulty × time), hand-offs on time, most improved, got ahead. Top 3 podium plus your own spot; nobody else's low rank is shown; weekly reset; opt-out |
| D55 | **Breaks are never tracked or scored** anywhere (no counts, badges or leaderboard). They exist only for health |
| D56 | **Log other work**: anything that isn't a task (calls, helping a coworker, fires) can be logged with time and difficulty so it counts toward the day and effort points |
| D57 | **Kudos**: send from Team activity; the person's manager is copied and it's saved to their profile ("Copy all for my review"). Managers see their team's kudos |
| D58 | **Reviewing suggested changes**: switch between "Changes highlighted", "Suggested version" and "Current live version". New stages green, changed amber with what changed on the card, removed red and crossed out; new connections green, removed connections red dashed; a "What changed" list jumps to each change |
| D59 | **+ New** menu opens aligned to the button's left edge and shifts to stay on screen |
| D60 | **Builder on phones**: tap a stage's round handle, then tap the stage that should follow (tap-to-connect); drag also supports touch; "When this is done, also start an existing stage…" gives a no-drag way to connect |
| D61 | **Flow editor layout**: the diagram fills the screen; the editor is a slide-over panel on wide screens and a bottom sheet on phones, shown only when a stage, connection, flow details or change list is open |
| D62 | **Zoom**: Fit to screen, − / + and pinch or trackpad zoom; below 70% cards switch to a simplified view (title and owner). An overview map shows where you are and jumps on tap when the flow is bigger than the screen |
| D63 | **Full screen** hides the page bar and tab bar; it is on by default on phones and short landscape screens, with Back and Save in the toolbar |
| D64 | **Step list** view: the same flow read top to bottom by step, parallel stages grouped, with waits-for / then-starts / receives on each card; editable. Default on phones held upright; a one-time hint suggests turning sideways |
| D65 | **Path highlight**: selecting a stage highlights everything it waits on and everything it starts; the rest fades. Clicking empty canvas clears it |
| D66 | Empty lanes collapse to a thin row; long hints and legends hide on small screens; the suggester's note folds behind "Read their note" |
| D67 | **Scrolling always wins on touch**: a normal swipe anywhere on the diagram scrolls it, even when it starts on a stage. Moving a stage on a phone needs a press and hold (the card lifts and the phone gives a short buzz). With a mouse, drag empty space to pan; dragging a stage still moves it. Dragging near an edge scrolls the diagram |
| D68 | **Later pocket** (one feature: the pocket and its wrinkled-paper reminders). A note icon at the top, "Jot for later" on the Now card and "Jot a thought" in + New capture a thought in one step. Saved with it: day and time, the task you were on and whether you'd just started or how long you'd been at it, the step you were on, a task you'd just finished, a break if you were on one, the page you were on, and optionally what was playing. Tagged Work hours, Home hours or Any time, and it only reminds you during those hours. **You choose the first reminder** (5 min to 8 hr, or any number of minutes). The note comes back as a scrap of paper; each snooze halves the wait and crumples the paper more. Once the next wait would be under 5 minutes there is no snooze: make it a task (prefilled, with the saved moment in its notes), add it to a task as a note or step, or toss it. Example: 1 hr, then 30, 15, 8 min, then decide |
| D69 | **What's playing**: entered by hand in the prototype. In the real app, Android can fill it in automatically with notification-access permission, and a browser extension can on a computer. iPhone only exposes Apple Music's own player, so other apps need typing or pasting a link |
| D70 | ~~Wrinkled-paper reminders as a separate feature~~ merged into D68 |
| D71 | **Light days** replace cycle-aware planning. Any day can be made light from its column header, and Cueue never asks why. Tasks that aren't due and aren't top priority move to the next regular day (Undo brings them back); breaks come every hour at most, there's at least 10 minutes between tasks, and urgency cues stay a soft glow with no shaking |
| D72 | **Weekly mantras** replace fresh-start prompts: 26 short sayings rotating every Monday, starting with "One day, or Day One?" and "Don't put it down. Put it away." Shown at the top of Today with "I used it". End day opens a close-out check-in (did you use it, plus an optional private moment); on Sunday it also asks for a meaningful use that week |
| D73 | **Mantra rewards**: lifetime count of days used, milestones at 10, 25, 50, 100, 250 and 500, per-mantra totals, a favorite, and a "year in mantras" recap. Saved moments are private by default and shared only when the person picks friends, family or coworkers for that story |
| D74 | **Reading style** (Settings, Reading). Verbs heavy bold, nouns underlined, describing words in italics. Default is **Key words**: in each phrase only the action and its main noun are marked ("**Send** the signed **contract**"). "Every word" marks all of them; "Plain" turns it off. Based on research in doc 08: marking a few key words helps; marking everything doesn't |
| D75 | **Variable weight**: small linking words (the, to, of, up) are lighter, so the content words stand out. On by default, can be turned off |
| D76 | Styling applies to things you read (task titles, steps, notes, Later notes, stories), never to text you're typing, headings, buttons or labels. Underlines are thick, soft and offset so they don't look like links; links in the app must never rely on underline alone |
| D77 | **Focus read**: notes can be read one short phrase at a time in a single spot (slow, medium or fast, tap to pause), based on a 2025 study where this improved comprehension for readers with ADHD |
| D78 | In the real app, part-of-speech tagging runs on the device: Apple's Natural Language framework on iPhone and iPad; a small on-device tagger on Android and the web. The prototype uses a word list and simple rules, so it gets some words wrong |
| D79 | **Done so far** on the Now card: an arrow opens the steps already checked in this task and the tasks already finished for the same goal. Each has Undo or Reopen |
| D80 | **Roadblocks**: any task (from its details or the Now card) can get a roadblock: what kind, what happened, expected delay and what would help. Everyone in the task's goal or flow is pre-selected (who started it, stage owners, and stages that wait on it first); anyone else in the org can be added. They see a preview before it's sent. The card gets a Roadblock chip, the flow's goal card shows the latest update, and "It's cleared" sends a back-on-track update to the same people |
| D85 | **Task details = what the task is.** Shows: goal, title, one line of facts (area, difficulty, estimate, priority if high, repeat, due), roadblock or waiting note, Done when, steps (checkable), notes with Focus read, contact (one line, opens CRM), files. History, contact log, source email and research fold into "History & background". Actions: Start/Complete, Edit, then Waiting on someone and Report a roadblock |
| D86 | **Editing lives behind Edit**: title, Done when, estimate, goal, difficulty, priority, area, proof required, steps (add, remove, suggest), notes, files and Delete. "Done" returns to the read view |
| D87 | **Roadblocks name who we're waiting on.** The form shows which task it's for (marked "Current task" from the Now card) and lets you pick the person: the task's own contact first, then coworkers in the flow, CRM candidates, vendors and clients, other contacts and coworkers, with search, or type someone else. "Have you reached out?" records Called / Emailed / Texted / Left a message / Talked in person with the time, and can set a follow-up reminder (1 hr, 3 hr, tomorrow) in the Later pocket. The roadblock note shows who, every contact attempt (or "Not contacted yet"), Log contact, and Open in CRM. Attempts also go into the task's contact log |
| O8 | Possible new homes for task info: full contact history in CRM; completion history and badges in Achievements/Insights; research notes in Templates & ideas; source email in a future Inbox/Sources view; time tracking in Insights |
| O7 | Visual direction: crisp white base plus hanging times, goal icon tiles, floating bars, pressable reward buttons, no breakable streaks (docs/style-directions.html). Proposed five selectable styles (Paper, Calm, Glass, Bold, Night) that share one layout and keep the visual clock everywhere; mockups of Today, menu, task details, Flows hub and flow diagram in docs/screen-styles.html. Waiting on the owner's choice |

## Open
| # | Question |
|---|---|
| O1 | Final name for "Span" |
| O2 | App name: working name **Cueue** (Cue, Kairo taken; Day One conflicts with the journaling app). Trademark check pending |
| O3 | Rollover prompt threshold (start at 3) — tune after real use |
| O4 | Exact cue escalation levels and defaults — tune in prototype |
| O6 | Meaning of color coding beyond status (e.g. energy level, goal color) — revisit after use |
| O5 | Exact re-plan behavior when the current task runs long — test in prototype |
