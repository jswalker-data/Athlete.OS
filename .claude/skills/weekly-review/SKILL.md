---
name: weekly-review
description: Review Josh's last training week — pull real Garmin data (not just whether he showed up), judge it against training/plan.md's intent for that phase/week, reconcile it with how the week actually felt (asked directly, not assumed), and check it against trends in past reviews/. Writes a short, decision-focused review dated to reviews/ and proposes one or two adjustments for next week, each with a reason. Use when Josh asks for a "weekly review", "review my week", "how did last week go", or runs /weekly-review.
---

# /weekly-review — judge the week that just happened

This is not a mileage recap. It is the weekly close-out of the Coaching
Philosophy in `athlete-profile.md`: did the week do its job for the current
phase, not just did the sessions happen. A review that only restates Garmin
totals is not useful — the value is in the gaps: planned vs. actual, feel vs.
data, and this week vs. the trend across past reviews.

## What "the week" means

Default to the most recently **completed** Monday-Sunday week (i.e. not the
week in progress). Cross-check against `training/` for the matching dated
plan file (`training/<Monday>-week.md`) — that file, if it exists, is the
literal intent to judge against. If no dated plan file exists for that week
(e.g. it predates `training/plan.md`, or a plan was never written for it),
say so explicitly in the review rather than inventing an intent — judge it
instead against `plan.md`'s phase-level goals and the "load capacity" /
limiter framing, and flag clearly that no specific weekly plan existed.

## Process

### 1. Read past reviews first
List `reviews/` and read the most recent 2-3 (or all, if fewer exist). This
is not optional context — it's how a single bad night's sleep gets correctly
read as noise versus how a third straight week of the same HR drift gets
correctly read as a trend. Note anything from past reviews' "adjustments for
next week" and check whether they actually happened this week.

### 2. Read the standing context
- `athlete-profile.md` — zones, injury history, limiters, hard rules.
- `training/plan.md` — current phase, this week's number in the build,
  what this phase/week was supposed to accomplish.
- `training/<Monday>-week.md` for the week being reviewed, if it exists —
  the literal day-by-day intent (session types, target efforts, the "why"
  for key sessions, any sequencing notes already flagged as risk).

### 3. Pull the real week from Garmin
Use `garmin_mcp` for the 7 days being reviewed, plus a few days of trailing
context on either side:
- `get_activities_by_date` for the week — every activity, not just runs
  (strength counts too).
- For each run, splits/HR detail (`get_activity_splits` or
  `get_activity_typed_splits`, `get_activity` for avg/max HR) — this is
  where "was easy actually easy" and "did the long run drift" live, not in
  the summary distance/pace.
- `get_sleep_summary` (or `get_sleep_data` if summary is missing something
  material) for every night that week.
- `get_daily_steps` for the week.
- `get_all_day_stress` or `get_stress_summary` for the week.
- `get_training_readiness` / `get_morning_training_readiness` for the week.
- `get_hrv_trend` spanning this week plus 1-2 prior (single-day HRV is
  noise — the trend is the signal).
- `get_training_load_trend` (CTL/ATL/TSB/ACWR) spanning this week plus
  2-3 prior — this is the fatigue-accumulation check.

Compute or note explicitly:
- **Total volume and elevation** for the week.
- **Easy-day quality**: for every run tagged/intended as easy, actual avg
  HR vs. the Z2 124-144bpm band (per `athlete-profile.md`) at the pace it
  was run. A run that hit "easy pace" at Z3 HR is not an easy run — say so
  plainly, it's the specific failure mode this athlete's plan is built to
  fix.
- **Long run integrity**: did HR drift up materially in the back half
  (aerobic decoupling), or hold flat? Use splits, not just the average.
- **Key-session intent**: for any quality/hill/threshold session that
  week, did the actual effort match what was prescribed (right zone,
  right structure), not just "did a hard run happen."
- **Fatigue signals**: HRV trend vs. 7-day baseline (>10ms drop from
  baseline is the flag per the tool's own guidance), ACWR trend, resting
  HR trend if visible, sleep debt (nights under ~5-6h), any elevated
  stress days that cluster around low-readiness days.
- **Consistency**: sessions planned vs. sessions actually done, and any
  gap explained (or not) by the data — same lens as the founding profile's
  "consistency, not motivation, is the core problem" framing.

### 4. Ask Josh how the week actually felt
Don't skip this or infer it from the data. Ask directly — briefly, not a
long questionnaire — covering: energy, sleep (subjective, not just the
Garmin score), soreness (and specifically any joint pain per the
injury-history hard rule), stress, motivation, and which sessions felt
great or rough and why. Then explicitly reconcile: where does what Josh
felt match the data, and where does it disagree? A disagreement (felt
great on a day HRV/readiness was poor, or felt wrecked on a day everything
measured fine) is usually the most useful single thing in the review —
don't smooth it over, name it and offer a read on what it might mean.

### 5. Write the review
Keep it short and decision-focused, not a data dump. Structure:

1. **Planned vs. actual** — what `plan.md`/the dated week-file called for
   vs. what happened, in one compact table or tight paragraph. If no plan
   existed for this week, say that up front instead of comparing against
   nothing.
2. **How it really went** — volume/vert, easy-day quality, long-run
   integrity, key-session intent, using the specific numbers, not vague
   language ("mostly fine"). Cite dates and figures.
3. **Feel vs. data** — Josh's check-in reconciled against the Garmin
   picture; call out any disagreement explicitly.
4. **Flags that matter** — overtraining/injury-risk signs (per the
   CLAUDE.md hard rule, this is mandatory whenever present, not optional
   color), and respect the injury history explicitly if anything joint-
   related came up.
5. **Trend check** — anything confirmed or contradicted versus the last
   2-3 reviews, with the specific evidence (dates/numbers) backing it, not
   just a vibe ("still seeing the Z2/Z3 gap for the third week running,
   avg HR 151/158/154bpm on easy runs Jul 6/13/20").
6. **Wins** — name them plainly and specifically; this athlete explicitly
   wants real credit when it's earned, not just correction.
7. **Adjustments for next week** — one or two, each with the reason tied
   to the evidence above. Keep this tight; it's input to `/plan-my-week`,
   not a rewrite of the plan here.

Tone: direct, evidence-based, no flattery and no burying bad news — per
the "accountability, not flattery" preference in `athlete-profile.md`.
Effort/HR over ego, exactly as CLAUDE.md requires.

### 6. Save it
Write to `reviews/<Monday-of-reviewed-week>.md` (ISO date, e.g.
`reviews/2026-07-13.md`). **Never overwrite a past week's review** — the
history across weeks is the point (CLAUDE.md hard rule). If a review
already exists for that Monday, that means this is a re-run or correction
of the same week — confirm with Josh before touching it rather than
silently overwriting.

### 7. Close the loop
Present the review conversationally, don't just dump the file. If the
adjustments for next week are non-trivial, mention that they'll feed
`/plan-my-week` next time it runs rather than re-planning inline here.
