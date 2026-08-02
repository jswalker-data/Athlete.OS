---
name: time-predicter
description: Predict Josh's Ealing Half Marathon finish time three ways — likelihood of hitting his 1:42:00 target, projected finish if the race were run today, and projected finish if he sticks to training/plan.md through race day — grounded entirely in real Garmin data (race predictions, VO2max, actual race/long-run splits and HR) plus training/reviews/health files. Never a vibe number. Use when Josh asks "what time do you think I'll run", "what's my chance of hitting my target", "predict my race time", or runs /time-predicter — feeds the dashboard's race-prediction tiles.
---

# /time-predicter — three numbers, fully grounded

This produces exactly three numbers, every time:

1. **% likelihood of finishing in the target time** (1:42:00, or whatever
   `athlete-profile.md` currently has locked in).
2. **Predicted finish time if the race were run today.**
3. **Predicted finish time on race day**, assuming Josh follows
   `training/plan.md` with *realistic* (not perfect) adherence.

Every number must show its arithmetic and cite the specific data point it
came from. No number gets written down without a model or a real data
point behind it. This is a coach's reasoned estimate built from standard
exercise-science prediction models plus Josh's own demonstrated
performance — not a black-box statistical output, and the write-up should
never imply more precision than the data supports.

## Why this needs more than "ask Garmin"

Garmin's own `get_race_predictions` (VO2max/Firstbeat-derived) is a real
input, but `athlete-profile.md` already flags it as an **optimistic
ceiling, not a target** — and the data backs that up concretely: compare
Garmin's own algorithmic 5K prediction (live each run) against Josh's
actual best-ever 5K (21:40, Jul 18 parkrun, a genuine race effort with
max HR 196). If Garmin's current-day 5K prediction is faster than his
actual best at the *shortest*, least-endurance-dependent distance, that's
a measurable, quotable calibration gap — use it to discount the longer-
distance predictions, don't take them at face value.

The deeper problem is structural: VO2max-based predictors (Garmin's and
the standard Riegel/VDOT formulas alike) assume the runner has trained
fatigue-resistance at the target distance. Per `athlete-profile.md`'s own
ranked limiters, Josh's #1 and #2 limiters are exactly that — aerobic
efficiency and long-run ceiling, not raw speed. His 5K speed may predict
a fast half marathon; his demonstrated ability to *hold* effort past 6
miles says otherwise. This skill's whole job is reconciling that gap
honestly.

## 1. Gather the real data

**From Garmin (live, `garmin_mcp`):**
- `get_race_predictions` — today's algorithmic 5K/10K/HM/marathon times.
- `get_training_load_trend` or `get_vo2max_trend` — current VO2max and
  whether it's actually moved recently (a flat trend means no measured
  aerobic-capacity gain yet, regardless of training volume logged).
- `get_lactate_threshold` if available (running power-based FTP — useful
  supporting context, not a primary input for a runner without a power
  meter history).
- **Every genuine race effort on record** (`get_personal_record`, cross-
  checked against `athlete-profile.md`/past reviews for the actual best
  known distance-specific times, since Garmin's own PR list doesn't
  always tag informal races). Get the real splits (`get_activity_splits`
  or `get_activity_typed_splits`) and HR for each — not just the summary
  time.
- **The single longest continuous effort(s) on record**, race or not
  (check `get_personal_record`'s "Longest Run" and cross-reference
  `athlete-profile.md`'s injury history for any other long efforts, e.g.
  a past long run that led to injury). Pull full splits/HR for these —
  this is the only real evidence of how the athlete's HR/pace behaves
  when pushed toward race-adjacent distance, and it matters more than
  any formula.
- **Every long run and quality session from the current training block**
  (`training/` dated week files → cross-reference `get_activities_by_date`
  + splits) — specifically checking for HR drift/decoupling at distance
  (does HR climb while pace holds or increases, i.e. aerobic decoupling —
  not just "did the average land in Z2").
- Recent training-load/consistency picture (`get_training_load_trend`,
  weeks completed vs. planned per `training/` and `reviews/`).

**From the project files:**
- `athlete-profile.md` — locked target time, zones, ranked limiters,
  injury history.
- `training/plan.md` — remaining phases/weeks to race day, prescribed
  peak long run, prescribed quality-session cadence.
- `reviews/` — actual adherence history (sessions/weeks completed vs.
  planned, and *why* when they weren't — illness, life, injury).
- `races/*-dossier.md` — course profile (elevation gain matters: a
  rolling ~140m-gain course costs real minutes relative to a flat-course
  prediction; the standard rule of thumb is on the order of a few
  minutes for that much gain at recreational HM pace — apply a course
  adjustment, don't silently ignore it).
- Any `health/` flags — recent illness/injury that changes near-term
  trajectory.

## 2. Build "if raced today" (Number 2)

Compute multiple independent models from the **actual best real race
performance** (not Garmin's prediction of it):

- **Riegel formula**: T2 = T1 × (D2/D1)^1.06, from the actual best race
  time at the shortest reliable distance to the half-marathon distance.
  Note explicitly that Riegel is known to run optimistic for large
  distance-ratio extrapolations (5K→HM is a >4x jump) absent a
  demonstrated endurance base — treat its output as an upper bound, not
  the answer.
- **VDOT/Daniels tables cross-check**: convert the actual best race time
  to an approximate VDOT, read the table-equivalent HM time. This uses
  different underlying data (large-sample well-trained-runner
  correlations) than Riegel — where the two disagree, that gap itself is
  informative.
- **Garmin-calibrated estimate**: compute the ratio between Garmin's
  live algorithmic prediction for the athlete's best-known distance and
  his actual best real time at that distance (e.g. predicted-5K vs.
  actual-best-5K). Apply that same optimism ratio to Garmin's HM
  prediction. This corrects Garmin's own number using his own
  demonstrated execution gap — legitimate because it's evidence he
  personally generated, not a generic discount.

These three cluster into a **"speed ceiling"** estimate — what he could
run *if* he currently had race-adequate endurance depth at 13.1 miles.
He doesn't yet (see below), so this is not the final number.

**Apply the endurance-depth discount.** Look at the real HR/pace pattern
from his longest actual efforts (both the training-block long runs and
any pre-block long effort). If HR climbs materially while pace holds or
increases — aerobic decoubling — quantify the % HR rise from early to
late in that effort and treat a comparable magnitude as a real "tax" on
the speed-ceiling estimate for the full race distance: a runner who
can't hold flat HR/pace for 6 miles will pay a bigger tax over 13.1.
Cross-check: does the discounted number land near his one longest real
continuous-effort pace, if he has one? If the model and the lived data
converge, that's a strong signal the estimate is grounded correctly —
say so explicitly when it happens.

**Apply the course adjustment** (elevation gain, from the race dossier).

State the final "if raced today" figure as a point estimate **and** an
honest range, with the reasoning chain shown compactly (which models,
what discount, why).

## 3. Build "if the plan is followed" (Number 3)

Start from the "if raced today" speed ceiling and endurance-tax
breakdown. Reason explicitly about:

- **How much the remaining phases actually target the endurance-tax
  specifically** — `plan.md`'s long-run progression, quality-session
  reintroduction, and (per its own explicit reasoning) whether the peak
  long run reaches full race distance or relies on taper/adrenaline for
  the remainder. A plan that peaks well below race distance leaves a
  real residual tax on race day — don't erase it just because a plan
  exists.
- **A realistic (not zero, not full) adherence discount**, derived from
  Josh's *own* logged history in `reviews/` — count actual disruptions
  (illness, life events, injury) over the weeks logged so far, and use
  that as a base rate for remaining weeks, not an assumption of perfect
  execution. Weigh this against how well he's historically recovered
  from disruptions (per HRV/readiness data) — quick, clean bounce-backs
  argue for a smaller adherence penalty than repeated slow ones would.
- **Any plausible raw-speed gain** from quality sessions reintroduced in
  later phases — keep this modest and evidence-based (his VO2max trend
  tells you whether past training has actually moved this number; don't
  assume large gains just because a plan says so).

Show the combined arithmetic. State a point estimate and range.

## 4. Build the % likelihood (Number 1)

Compare the target time against the "if plan followed" distribution, not
against Garmin's raw optimistic number. Reason in plain terms about the
size of the gap (in minutes and as a %), and translate that into a
percentage using rough, stated judgment about race-day variance for a
recreational runner with limited race experience (a few-percent PB-day
outperformance is plausible; a much larger one is a tail event, not a
coin flip). **Do not present a falsely precise number** (a number like
"23.4%" implies false statistical rigor) — round to a sensible band
(e.g. "~15%", "~30%") and show the reasoning, not just the output.

If the honest answer is that the target now looks like a real stretch
given the current trajectory, say that plainly — per CLAUDE.md and
`athlete-profile.md`'s explicit "accountability, not flattery" ask. This
is exactly the kind of finding that must not get softened.

## 5. Save the analysis

Save the full reasoning (all models, all numbers, all citations to
specific activities/dates) to a dated file: `races/<date>-time-prediction.md`.
This is a snapshot, not a running document — a new dated file each time
this is re-run, same pattern as `reviews/`. Never silently overwrite a
previous prediction; each one is a data point for tracking whether the
projection is trending toward or away from the target over the
remaining weeks.

## 6. Feed the dashboard

If `dashboard.html` exists, hand the three headline numbers (with the
one-line "why" for each) to `/regenerate-dashboard` to display — don't
duplicate the full reasoning there, just the numbers and a short
citation-backed reason, linking implicitly to the dated file in `races/`
for the full math.

## 7. Re-run cadence

This isn't a one-time calculation. Re-run it every 1-2 weeks (naturally
alongside `/weekly-review` or `/plan-my-week`), and immediately after
anything that would materially move the inputs — a new PR, a new longest
continuous effort, an illness/injury event, or a VO2max change. Compare
against the last dated file in `races/` and say explicitly whether the
trajectory moved toward or away from the target and why.
