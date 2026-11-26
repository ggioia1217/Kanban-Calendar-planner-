# Gaps, Rewards and Evidence Check

What Cueue is missing, where research points for better focus, how to make rewards something
people love, and an honest check of the evidence for and against the design so far.
(Builds on docs 02, 05 and 06. Sources at the end.)

## The short version
1. **The biggest risk isn't a missing feature, it's people quitting.** Popular mental-health apps
   keep about 3% of users after 30 days (Baumel 2019). Cueue's first week matters more than its
   hundredth feature.
2. **Put the visual clock where you already look:** the lock screen, the Dynamic Island, the watch.
   Time blindness is the core problem, and right now the clock lives only inside the app.
3. **Rewards should be varied, immediate, partly surprising, and about progress, not prizes.**
   Research warns that expected, tangible "do X, get Y" rewards can erode a person's own
   motivation.
4. **Don't claim it treats ADHD.** Digital ADHD tools show small effects with low-quality evidence.
   Say "built on research," and plan to measure Cueue ourselves.
5. **Keep the calm defaults.** Shaking, red alerts and leaderboards can raise anxiety and shame in
   a group that already struggles with emotion regulation and rejection sensitivity.

## 1. What's missing from the product

### Must-have before launch
| Missing | Why it matters | Notes |
|---|---|---|
| **Lock-screen and Dynamic Island timer (Live Activity), Apple Watch taps** | Time has to be visible outside the app to help time blindness (Barkley's "externalize time") | Live Activities work from Expo with a small Swift extension, same as the widget |
| **Transition warnings** ("10 min left, then the Riverside call") | Switching tasks and remembering future events (prospective memory) are known ADHD weak spots | A gentle tap at 10 and 2 minutes before the next block, not just at the start |
| **A 2-minute first week** | Long setup is where ADHD users drop off | Day 1: add three things, press Start. Goals, flows, CRM and styles unlock as they're used |
| **"Today isn't working" reset** | A blown-up day often ends the app streak for good | One button: keep the 1 to 3 essentials, move the rest, no guilt. (Light day is close; this is the same-day panic version) |
| **Capture from anywhere** | Ideas and requests arrive in email, texts and conversations | Share sheet, voice note to task, email forwarding address, Siri/Shortcuts. Later pocket from the lock screen |
| **Distraction shield** | Focus is lost to the phone itself | Turn on an iOS Focus mode or Screen Time block during the current task (Apple's Screen Time API) |
| **Privacy and data controls** | Light days, medication times and moods are sensitive health-like data | Clear privacy screen, export, delete, no selling data; App Store privacy labels |

### Strong additions
| Idea | What it is | Evidence |
|---|---|---|
| **Focus rooms (body doubling)** | Join a quiet video or audio room, or work "alongside" a teammate or family member's live timer | Widely reported to help task start; research is small (12-person VR study, surveys). Make it optional; some people find social presence distracting |
| **Weekly review ritual** | 10 minutes on Sunday: what got done, what moved, pick next week's top three | Planning and review are core parts of CBT for adult ADHD (Safren, Solanto) |
| **"When-then" plans** | When planning, Cueue asks "When will you start?" and turns it into "When I finish lunch, I'll open the agreement" | Implementation intentions have one of the strongest evidence bases for follow-through (Gollwitzer) |
| **Energy and medication check-in** | A one-tap morning check (energy, sleep, meds taken) that adjusts the plan | Ties to the fresh-hours idea; also builds data people can share with a clinician |
| **Share with a coach or clinician** | A read-only weekly summary | ADHD coaching shows promising but mostly uncontrolled results; a summary makes sessions more useful |
| **Movement breaks that count** | Short walk or stretch options promoted after long focus blocks | Acute exercise improves attention and executive function short term (doc 06) |
| **Gentle sound options** | Brown, pink or white noise and lo-fi during focus | Mixed evidence (Nigg 2024 in doc 06): helps some, not others, so make it a choice |

### Business pieces that are easy to forget
- **Pricing and trial:** a free tier that's genuinely useful, a trial that doesn't punish a lapsed
  week, and an easy way to pause a subscription (ADHD users often forget renewals; goodwill
  matters).
- **Accessibility:** VoiceOver, Dynamic Type, color-blind-safe status colors (don't rely on red
  vs green alone), reduce-motion, dyslexia overlap.
- **Support and onboarding content:** short videos, not docs.
- **Team plan admin:** seats, billing, data ownership when someone leaves, and HR-safe settings
  (managers must never see light days or private notes).
- **Medical-claim rules:** stay a productivity app. Claims to "treat ADHD" would bring FDA and FTC
  rules into play.

## 2. Where research points for better focus

| Problem | What research suggests | What Cueue should do |
|---|---|---|
| Time blindness | Make time visible and external (Barkley) | Visual clock everywhere: Live Activity, widget, watch, plus transition warnings |
| Getting started | Big tasks feel worse than they are; tiny first steps and set start times help (CBT; Gollwitzer) | "Just the first 5 minutes" start button; first step always tiny; when-then prompts |
| Delay aversion | People with ADHD strongly prefer sooner rewards (Sonuga-Barke; delay discounting) | Reward every step instantly; show "done" visibly right away |
| Reading and attention | Showing text in one spot boosted comprehension for ADHD readers (Moussaoui 2025); signaling key words helps (Schneider 2018) | Keep Focus read and key-word styling (built) |
| Breaks | Fixed Pomodoro breaks vs breaks you choose: mixed results. Systematic breaks helped in one study (Biwer 2023); a 2025 study found Pomodoro raised fatigue faster with no productivity difference | Offer both: Cueue's 90-minute default, plus a "Flowtime" option where you keep going while it's working and break length grows with focus time |
| Emotion and shame | Emotion dysregulation is common in adult ADHD (Beheshti 2020) | Calm language, no "you failed," Light days, recovery rewards (below) |
| Mind wandering | Spontaneous mind wandering is high in ADHD (Seli 2015) | Later pocket captures the stray thought so you can return; a "where was I?" recap when you come back to a paused task |

## 3. Rewards people will love

### What the research says about rewards
- **Immediate beats delayed** for ADHD brains (delay aversion).
- **Novelty matters:** ADHD involves differences in how novelty and reward are processed (Sethi
  2018). The same chime every time loses its pull.
- **Expected "do this, get that" rewards can backfire:** across 128 experiments, expected
  tangible rewards lowered people's own interest in the task (Deci, Koestner & Ryan 1999).
  Surprise rewards and feedback about real progress don't carry that cost.
- **Gamification works, modestly:** small to medium boosts to motivation and behavior (Sailer &
  Homner 2020), but the motivation boost is less stable over time. Stories and
  competition-plus-teamwork helped most.
- **Broken streaks drive people away:** users who break a streak are more likely to quit
  entirely, especially when they blame themselves. Letting them repair it reduces the damage
  (Silverman & Barasch). One missed day doesn't hurt the habit itself (Lally 2010).

### A reward system in layers
| Layer | Examples | Why |
|---|---|---|
| **1. Instant feedback (every check)** | Several sound and animation variants that rotate, haptic tap, card visibly changing | Immediate; variety slows habituation |
| **2. Surprise moments (occasional, unannounced)** | "That was your fastest Monday start this month," a rare shiny check, a thank-you from future you | Unexpected rewards don't undermine motivation; surprise keeps novelty |
| **3. Visible progress** | Goal rings, a day bar that fills, a weekly "map" that lights up, flows moving forward | Progress feedback is informational, the healthiest kind of reward |
| **4. Collectibles and unlocks** | Unlock styles (cork board, dry-erase), sounds, mantra cards, stickers for the board | Choice and personalization; keeps the app fresh over months |
| **5. Your own rewards ("reward menu")** | Pick from your own list: coffee walk, a show episode, a game, after a chosen effort. "Temptation bundling": only listen to a favorite podcast during dull tasks | Person-chosen, so less controlling; temptation bundling raised gym visits in a field study (Milkman 2014) |
| **6. Meaning** | "Your hand-off started Payroll's work," kudos, mantra stories, who you helped | Connects effort to impact, which lasts longer than points |
| **7. Comeback rewards** | After a rough day or a gap, the first task back gets a special welcome-back moment; Light days count as "taking care of yourself" | Re-entry is where ADHD users quit; reward returning, never shame the gap |

**Avoid:** losing points, streaks that reset to zero, public bottom ranks, guilt notifications
("You haven't opened Cueue in 3 days!"), and rewards that cost real money to unlock.

## 4. Evidence check: what supports the current design

| Cueue feature | Supporting research | Strength |
|---|---|---|
| Steps for every task, tiny next step | CBT for adult ADHD teaches breaking tasks down and planning (Safren 2010; Solanto 2010) | Strong (RCTs of the full therapy, not of apps) |
| Visual clock and time-aware day | Time-perception differences in ADHD; Barkley's model of externalizing time | Good theory, moderate evidence |
| Instant rewards on each step | Delay aversion and steep delay discounting in ADHD (Sonuga-Barke; Jackson & MacKillop 2016) | Good |
| Routines and "missing a day is fine" | Habits took about 66 days on average and a missed day didn't undo progress (Lally 2010) | Good |
| Later pocket | Mind wandering and prospective memory difficulties in ADHD | Good theory; no app trial |
| Breaks with movement | Acute exercise improves attention short term (meta-analyses in doc 06) | Moderate |
| Key-word styling, Focus read | Signaling meta-analysis; 2025 RSVP study in ADHD | Moderate (styling), early (Focus read) |
| Light days | Emotion dysregulation and fluctuating capacity in adult ADHD | Theory-based; worth measuring |
| Mantras | Self-talk and if-then cues; no direct ADHD study | Weak; keep it light and optional |
| Body doubling (proposed) | Surveys and small studies only | Weak but popular |
| Digital ADHD tools overall | 23 RCTs: small symptom effect (g ≈ −0.32), low-quality evidence; adult app trials are rare | Small; don't over-claim |

## 5. Evidence check: what may need fixing

| Risk | Evidence | Fix |
|---|---|---|
| **People stop using it within weeks** | About 3% 30-day retention in popular mental-health apps (Baumel 2019) | Minimal day-1 setup, progressive unlocks, comeback rewards, no guilt messages, measure 7- and 30-day retention from day one |
| **Too many features at once** | ADHD working-memory load; every option is a decision | Hide advanced features (flows, CRM, styles) until used; one primary action per screen |
| **Shaking and red alerts raise anxiety** | Emotion dysregulation is common in adult ADHD | Keep gentle as default; shaking opt-in; cap urgency on light days (done) |
| **Leaderboards hurt some people** | Social comparison and rejection sensitivity | Keep opt-in, effort-based, never show bottom ranks (done); add team goals that everyone fills together |
| **Expected rewards can erode motivation** | Deci, Koestner & Ryan 1999 | Make most rewards surprise or progress feedback; let people choose their own real rewards |
| **Fixed 90-minute breaks may not fit everyone** | Mixed results on fixed vs flexible breaks | Offer Flowtime-style flexible breaks as an option |
| **AI time estimates will be wrong at first** | People underestimate tasks (planning fallacy), and people with ADHD more so | Show estimates as ranges early ("30 to 50 min"), learn from real times, say "learning" until confident |
| **Proof required by default may add friction at home** | Every extra step lowers completion | Proof on by default for work flows only; off for home |
| **Over-claiming science** | Weak app-specific evidence; regulators police health claims | "Designed with ADHD research in mind," with sources; no symptom claims |
| **Sensitive data** | Light days, meds and moods are health-adjacent | Keep private by default; managers never see them; encryption and export/delete |

## 6. Suggested next steps
1. Add the **Live Activity / widget visual clock** and **transition warnings** to the Phase 1 plan.
2. Design the **first-week experience** (2-minute setup, progressive unlocks, comeback rewards).
3. Build the **layered reward system** in the prototype: rotating feedback, surprise moments,
   unlockable styles, a personal reward menu.
4. Add **Flowtime breaks** and a **"Today isn't working" reset** as options.
5. Plan a **small study**: track 30-day retention and self-rated focus with early users; ideally
   partner with a university ADHD researcher.

## Added: how long should the shield pause be?
- **A 10-second delay works, and the way out matters most.** In a six-week study of the one sec app, a
  10-second pause before social apps opened led people to close the app 36% of the time and cut
  openings by 57%. A follow-up experiment found the strongest part was the option to back out, not
  the message shown during the pause (Grüning et al., PNAS 2023). A larger real-world study of 1,039
  users found these short frictions made app opening more intentional over time (Haliburton et al.,
  CHI 2024).
- **Exhale-focused breathing calms fastest.** Five minutes a day of "cyclic sighing" improved mood and
  lowered breathing rate more than mindfulness meditation in a month-long randomized study (Balban
  et al., 2023). Slow breathing (about 6 breaths a minute) raises heart-rate variability; single
  sessions show mixed effects on craving.
- **What Cueue does:** 15 seconds (two cyclic sighs) by default, adjustable to 10 or 30, with
  "Back to my task" always available immediately.
- **Medication timing:** no peer-reviewed studies were found on apps that track ADHD medication
  timing. Existing apps use estimated curves. Cueue learns each person's focus window from their
  own check-ins instead, and never claims to know drug levels.

## Sources
- Grüning, Riedel & Lorenz-Spreen (2023), one sec, *PNAS*: https://pmc.ncbi.nlm.nih.gov/articles/PMC9974409
- Haliburton et al. (2024), design frictions in the wild, CHI:
  https://www.medien.ifi.lmu.de/pubdb/publications/pub/haliburton2024chi/haliburton2024chi.pdf
- Balban et al. (2023), brief structured respiration, *Cell Reports Medicine*:
  https://pmc.ncbi.nlm.nih.gov/articles/PMC9873947
- Baumel et al. (2019), mental-health app retention, *JMIR*: https://www.jmir.org/2019/9/e14567
- Digital interventions for ADHD meta-analysis, 23 RCTs (2025), *BMC Psychiatry*:
  https://doaj.org/article/789ef3c13fd143468097858bb49f61e5
- Digital CBT apps for ADHD, systematic review (2025): https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12436941/
- Adult ADHD digital tools, UK evaluation (Bosnic et al. 2024):
  https://strathprints.strath.ac.uk/89559/
- Deci, Koestner & Ryan (1999), rewards and intrinsic motivation, *Psychological Bulletin*:
  https://pubmed.ncbi.nlm.nih.gov/10589297/
- Sailer & Homner (2020), gamification meta-analysis, *Educational Psychology Review*:
  https://link.springer.com/article/10.1007/s10648-019-09498-w
- Sethi et al. (2018), novelty and reward in adult ADHD: https://pmc.ncbi.nlm.nih.gov/articles/PMC5917772
- Streaks and quitting (Silverman & Barasch), INSEAD summary:
  https://knowledge.insead.edu/marketing/consumer-streaks-are-motivating-the-key-is-keeping-them-alive-19011
- Breaks: Smits, Wenzel & de Bruin (2025), Pomodoro vs Flowtime vs self-regulated:
  https://pmc.ncbi.nlm.nih.gov/articles/PMC12292963/
- Body doubling in VR, 12 adults with ADHD (2025): https://arxiv.org/html/2509.12153v1 ; CHADD
  overview: https://chadd.org/adhd-news/adhd-news-adults/could-a-body-double-help-you-increase-your-productivity/ ;
  Popular Science: https://www.popsci.com/health/body-doubling-focus-benefits/
- ADHD coaching for adults (Kubik 2010): https://pubmed.ncbi.nlm.nih.gov/19276311/ ; college
  students (Prevatt 2013): https://pubmed.ncbi.nlm.nih.gov/23509112/
- Moussaoui et al. (2025), reading without eye movements in ADHD: https://pubmed.ncbi.nlm.nih.gov/41277242/
- Earlier sources (Barkley, Safren, Solanto, Gollwitzer, Lally, Sonuga-Barke, Beheshti, Seli,
  Nigg, Milkman temptation bundling) are cited in docs 02, 05 and 06.
