---
name: plan-my-week
description: Build Josh's coming training week — grounded in his actual recent Garmin data, his current training/plan.md phase, and real training science (polarized 80/20, hard/easy alternation, progressive overload, the 10% rule and its limits). Sequences sessions properly, holds volume to a safe increase, explains the "why" behind each key session, saves a dated file to training/, then walks Josh through it and asks what changed before he commits. Use when Josh asks to "plan my week", "plan this week", "what's this week look like", or runs /plan-my-week.
---

# /plan-my-week — build the coming training week

This is not a template-filler. It is the weekly application of the
Coaching Philosophy in `athlete-profile.md`, run through real training
science and Josh's actual recent data. Every week it produces should be
defensible: grounded in evidence, grounded in what Josh actually did (not
what the plan assumed he'd do), and explicit about its own constraints.

## The training science this is built on

These are load-bearing, not decoration — apply them, don't just cite them.

**1. Polarized / 80-20 intensity distribution.** Stephen Seiler's research
across elite endurance athletes (cycling, rowing, running, XC skiing) found
the consistent pattern was ~80% of *sessions* easy, ~20% hard, with very
little time in the "grey zone" between. The 80/20 split is counted by
session, not by time or distance — one hard run out of four sessions a
week is already a ~75/25 split. Most amateurs blur this by running easy
days too hard, which thins the gains from both ends.
([Roadman Cycling: Seiler 80/20](https://roadmancycling.com/blog/stephen-seiler-80-20-polarised-training-cyclists),
[Outside: The Case For (and Against) Polarized Training](https://www.outsideonline.com/health/training-performance/polarized-training-debate/),
[TrainingPeaks: Does Polarized Training Really Work?](https://www.trainingpeaks.com/blog/does-polarized-training-really-work/))
→ **Applied here:** count quality sessions, not quality kilometers. Josh's
easy runs currently sit at 151-166bpm (Z3), not Z2 — until that gap
closes, every "easy" run is secretly encroaching on the 20%, which is
exactly the failure mode this research warns about. Flag this if recent
Garmin data still shows it.

**2. Hard/easy alternation and the 48-hour recovery window.** Adaptation
happens during recovery, not during the stress itself — roughly 48 hours
is the minimum to restore muscle glycogen and enzyme levels after a hard
effort, and timing the next hard session to land during the
supercompensation window (rather than before or long after it) is what
makes the alternation work. The practical rule of thumb: no more than
2 hard sessions a week, never back-to-back, with at least one full easy
or rest day between.
([McMillan Running: The Most Basic Law of Training](https://www.mcmillanrunning.com/the-most-basic-law-of-training/),
[Fleet Feet: Why You Should Take Your Easy Days Easy](https://www.fleetfeet.com/s/columbus/resources/why-you-should-take-your-easy-days-easy/),
[Science of Running: The In-Between Training Day](https://www.scienceofrunning.com/2019/07/not-hard-not-easy-the-in-between-training-day.html))
→ **Applied here:** quality session, long run, and hard-effort parkrun
are all "hard" for this purpose — never schedule two of them within 48
hours of each other.

**3. Progressive overload and recovery weeks.** You can't add overload
every week indefinitely; periodization pre-plans volume/intensity waves
so adaptation outpaces fatigue instead of being buried by it. The most
common structure is a 3:1 ratio — three weeks of progressive build,
one recovery/cutback week — with well-recovering athletes sometimes
extending to 4:1.
([CorrerJuntos: Running Periodization Guide](https://www.correrjuntos.com/blog/en/running-training-periodization),
[Fit Besides Health: Deload Weeks](https://fitbesideshealth.com/deload-weeks/))
→ **Applied here:** check `training/plan.md`'s phase table for where this
week sits in that wave (this plan currently runs roughly 3 build weeks to
1 lighter week per phase). Don't stack another volume increase onto a
week that's already supposed to be a cutback.

**4. The 10% rule — real, but weaker evidence than its reputation.** The
10%/week cap is a popular heuristic, but the evidence for it as a hard
threshold is thin. One study of novice runners found injury-free runners
averaged a 22% weekly increase — roughly double the "rule." Risk rises
more clearly above ~30% increases than around 10-20%, and well-trained
recreational runners may tolerate ~25% for short periods, while true
novices are the group the conservative number actually protects.
([Outside: The Myth of the 10 Percent Rule](https://run.outsideonline.com/training/getting-started/myth-of-the-10-percent-rule/),
[JOSPT: Excessive Progression in Weekly Running Distance](https://www.jospt.org/doi/10.2519/jospt.2014.5164),
[PMC: Training Load and Running-Related Injuries systematic review](https://pmc.ncbi.nlm.nih.gov/articles/PMC6253751/))
→ **Applied here:** CLAUDE.md's hard rule (never break the ~10% cap
without saying why) stays in force regardless — Josh's injury came off a
low base with an active knee/hip history, which is exactly the profile
the conservative number is *for*, not a case for stretching it. Use this
research only to explain *why* 10% is the number, and to know that if a
week must come in under 10%, that's not overly cautious — it's the
appropriate cap for this athlete, not a hedge to apologize for.

## What Josh told us this shapes on top of the science

(Captured 2026-07-20; re-confirm if it's been a long time or something
about his life has clearly changed.)

- **Quality session count:** not fixed — decide it fresh each week from
  the current `training/plan.md` phase and recent readiness/HRV/sleep
  data. Phase 1 (Aerobic Repair) = 0 quality sessions, full stop, per
  van den Broek's no-anaerobic-before-the-base-is-earned rule already in
  the Coaching Philosophy. Phase 2 onward = 1 quality session/week by
  default (matches `plan.md`'s own template); only consider 2/week if the
  Z2 aerobic-efficiency gap has genuinely closed (easy runs actually
  sitting in 124-144bpm, not just at "easy" pace) AND HRV/readiness has
  been consistently good with no accumulated fatigue signal. When in
  doubt, stay at 1 and say why.
- **Long run day:** defaults to **Sunday**, matching `plan.md`'s
  template and the natural post-parkrun recovery gap. Not locked — see
  next point.
- **Structure: fully flexible.** Josh explicitly wants days reshuffled
  week to week if that's what recent sleep/life/readiness data calls
  for, not just session effort downgraded in place. Don't default to a
  rigid Mon/Tue/Wed skeleton out of habit — actually look at the last
  1-2 weeks before deciding placement.
- **Loves:** hills (whenever access allows) and racing parkrun hard.
  No disliked sessions flagged. Tension to hold explicitly: `plan.md`'s
  Phase 1 template calls for parkrun as *controlled effort, not a time
  attack* — that's still the standing rule while the aerobic base isn't
  closed yet. Don't silently override it just because Josh likes racing
  it; if the data says the base is still open, say the phase rule wins
  this week, and name Saturday as the week the leash comes off once
  Phase 2 starts.
- **Hard no:** Thursday evenings. Mornings work. Comfortable range:
  3-5 sessions/week.
- **Units: miles, not km.** Josh doesn't like km (2026-07-20). Present
  every distance in miles (paces as min/mile). `training/plan.md`'s
  original figures are km-derived — convert for display, don't
  re-derive, and it's fine to show the km figure in parentheses once
  where it materially helps (e.g. matching a race's official distance)
  but miles leads everywhere.
- **Strength sessions must be fully specified, not a placeholder.**
  "Strength AM" on its own is not a finished plan — every strength
  session in the week must name the actual exercises, sets/reps (or
  hold time), tempo/cues, and total duration, so Josh can open the file
  and go straight into it with no re-explaining needed (2026-07-22).
  Use the **Strength session menu** below rather than inventing new
  exercises each week, so the sessions stay consistent and trackable.
- **Strength and running can share a day.** Josh is open to doing a
  strength session and a run on the same day whenever his schedule
  allows it (2026-07-22) — this is a real option for fitting sessions
  in around a blackout day or a busy stretch, not just a fallback.
  Still respect effort ordering (strength after an easy run is fine;
  avoid stacking strength right before a quality/long/race effort on
  the same day) and don't default to combining just to compress the
  week — only do it when it actually solves a real constraint that
  week.

## Strength session menu

Bodyweight only, no gym (per `athlete-profile.md`), ~25-30 minutes,
targeting knee/hip resilience per Josh's explicit ask. Alternate A/B
week to week so the same session doesn't repeat back-to-back. Present
whichever is used in full in the week file — exercises, sets/reps,
tempo, and a one-line cue each — not just the label.

**Session A — Glute & hip stability**
1. Glute bridge — 3×12, 2s pause at the top. *Cue: squeeze glutes, not
   lower back.*
2. Single-leg glute bridge — 2×10 each side. *Cue: keep hips level,
   don't let the free side drop.*
3. Clamshells (band-free) — 2×15 each side. *Cue: slow, controlled,
   no rocking the pelvis.*
4. Side-lying leg raises — 2×12 each side. *Cue: leg stays in line
   with the body, don't swing it forward.*
5. Standing single-leg balance — 2×30s each side (close eyes for the
   last 10s if it's easy). *Cue: this is boring on purpose — it's
   building the stability that protects the hip under fatigue.*
6. Side plank — 2×20-30s each side. *Cue: hips lifted, straight line
   shoulder-to-ankle.*

**Session B — Quad/patellar control, calf, core**
1. Spanish squat or wall sit — 3×30-40s. *Cue: knees tracking over
   toes, weight through the heels — this is the patellar-tendon
   builder, don't rush it.*
2. Step-downs (off a low step/stair) — 2×10 each side, slow. *Cue:
   control the descent, don't just drop — this is eccentric control,
   the part that actually protects the knee on downhills.*
3. Single-leg calf raise — 3×12 each side. *Cue: full range, pause at
   the top.*
4. Bird-dog — 2×10 each side. *Cue: opposite arm/leg, keep hips
   square, don't rotate.*
5. Dead bug — 2×10 each side. *Cue: lower back stays flat on the
   floor throughout.*
6. Standing hip flexor stretch + calf stretch — 30s each side, to
   close out.

Both sessions are AM-only per Josh's Thursday-evening hard no and
general morning preference, and neither should be scheduled directly
before a quality/long-run/race effort the same day if combined with a
run — do the run first, strength after.

## Process

### 1. Read the standing context
- `athlete-profile.md` — goals, zones, injury history, the full Coaching
  Philosophy section, hard rules.
- `training/plan.md` (or whatever the current phase plan file is named)
  — which phase and week number today falls in, that phase's prescribed
  weekly volume/long-run/template, and the non-negotiable rules section.
- List `training/` for existing dated weekly files (`training/YYYY-MM-DD-week.md`)
  — read the most recent 1-2 to see what was actually prescribed last
  time, so this week's volume baseline can be checked against it.

### 2. Pull the real picture from Garmin (not the plan's assumption)
Use `garmin_mcp` for the last 14 days, minimum:
- Activities (`get_activities` / `get_activities_by_date`) — what actually
  ran, real distance, pace, average HR per run (to check the Z2/Z3 gap).
- Sleep (`get_sleep_data` / `get_sleep_summary`).
- Training readiness / HRV (`get_training_readiness` or
  `get_morning_training_readiness`, `get_hrv_data` or `get_hrv_trend`).
- Stress (`get_stress_data` or `get_all_day_stress`).
- Training load/status (`get_training_load_trend`, `get_training_status`).

Compute **actual total running volume for the last 7 days** — this, not
the plan's prescribed number, is the baseline the 10% cap applies to.
If Josh ran less than prescribed, the cap applies to what he actually
did, not what the plan wished he'd done — compounding a missed week's
"planned" volume forward is exactly how the 10% rule gets silently
broken.

### 3. Decide this week's quality-session count
Apply the phase logic above. State the phase, state the count, state why
in one line.

### 4. Lay out the week, day by day
For each of the 7 days, decide: session type, target effort/pace (as a
range, van den Broek-style — see Coaching Philosophy), duration/distance.
Sequencing rules, all non-negotiable:
- No two hard efforts (quality / long run / race-effort parkrun) within
  48 hours of each other.
- Long run defaults Sunday; move it only if this week's actual data
  (bad sleep stretch, a known conflict, an already-hard Saturday) gives
  a real reason — say the reason if you move it.
- Strength sessions AM only, never Thursday evening, targeting knee/hip
  per the profile ask. Pull the actual exercises/sets/reps from the
  **Strength session menu** above — never leave a strength session as
  just a label. Combining a strength session with a run on the same day
  is fine when it solves a real scheduling constraint (run first,
  strength after).
- Respect the 3-5 sessions/week comfortable range unless Josh says
  otherwise this week.
- Total weekly volume ≤ last actual week's volume × 1.10, AND ≤ whatever
  `plan.md`'s phase table prescribes for this week — take the lower of
  the two. **If the 10% cap is the binding constraint and it's holding
  the week below what `plan.md` wanted, say so explicitly** — this is
  the CLAUDE.md hard rule in action, not a thing to bury in a table.

### 5. Explain the key sessions
For the long run, the quality session (if any), and anything unusual
(a moved day, a cut week, a reintroduced hill session) — one or two
sentences on why it's there and what it's building toward the 2026-09-27
Ealing Half Marathon target, tied to the specific limiter it's
addressing (see `athlete-profile.md`'s "Limiters, ranked").

### 6. Save it
Write to `training/<Monday-of-this-week>-week.md` (ISO date, e.g.
`training/2026-07-21-week.md`). **Never overwrite an existing dated
file** — if one already exists for that Monday, that's the draft Josh
is mid-review on; update it in place during the walkthrough conversation
in step 7, don't fork a second file for the same week.

Structure the file as: phase/week context, the day-by-day table, the
"why" for key sessions, the 10%-cap note (even if it wasn't binding —
say "not binding this week" so the rule is visibly still being checked),
and anything flagged as open (e.g. the parkrun controlled-vs-race
tension, a hill-route gap).

### 7. Walk Josh through it, then ask what changed
Present the week conversationally — don't just dump the table and stop.
Then explicitly ask: **what's changed this week?** (travel, life,
sleep you already know is coming, how the body's actually feeling) —
before treating the plan as final. If Josh's answer changes anything,
revise the same file, don't create a new one. This step exists because
the plan is a starting draft grounded in the *last* two weeks' data, not
a forecast of this coming week's life — Josh is the one who closes that
gap.
