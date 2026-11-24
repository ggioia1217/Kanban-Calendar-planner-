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
| D23 | Heavy task completion triggers a reward break; working past the break interval triggers a break |
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

## Open
| # | Question |
|---|---|
| O1 | Final name for "Span" |
| O2 | App name: working name **Cueue** (Cue, Kairo taken; Day One conflicts with the journaling app). Trademark check pending |
| O3 | Rollover prompt threshold (start at 3) — tune after real use |
| O4 | Exact cue escalation levels and defaults — tune in prototype |
| O6 | Meaning of color coding beyond status (e.g. energy level, goal color) — revisit after use |
| O5 | Exact re-plan behavior when the current task runs long — test in prototype |
