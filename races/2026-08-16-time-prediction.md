# Race Time Prediction — Ealing Half Marathon, snapshot 2026-08-16

_Built via /time-predicter | Target: 1:42:00 (locked 2026-07-20, re-confirmed 2026-08-10) | 42 days to race day (2026-09-27) | Supersedes `races/2026-08-10-time-prediction.md`_

## The three numbers

| | Time/likelihood | Range | vs. Aug 10 |
|---|---|---|---|
| **Likelihood of hitting 1:42:00** | **~17%** | ~13-21% | ▼ from ~18% (first snapshot to move the wrong way) |
| **If the race were run today** | **1:53:00** | 1:48-1:59 | ▲ from 1:54:00 |
| **If plan.md (v2) is followed (realistic adherence)** | **1:49:00** | 1:44-1:57 | ↔ flat, range widened |

**Mixed trajectory this cycle, and worth saying plainly:** the endurance/durability picture keeps improving (a second under-Z2-ceiling long run, this one longer and run under harder conditions), but the pacing-discipline picture — now the #1 named limiter — got worse, not better, for the third straight week. Those two forces roughly cancel out. This is the honest read, not a "still trending up" story.

## What changed since Aug 10 (why the numbers moved)

1. **The Aug 16 long run: 8.61mi, walk-run, HR 129→139→137→135→138→134→137→142→143bpm.** Longer than Aug 10's 8.0mi, and run the morning after an all-out race on a LOW readiness score (49) — a genuinely harder starting condition than Aug 10's fresh-legs consolidation run. **This is not a perfectly flat trace like Aug 10's** — there's a mild ~11% rise from first mile to last (129→143) — but it never left the Z2 ceiling (144), under real fatigue. Read: slightly weaker evidence than "zero drift again," but arguably a tougher and more informative test passed.
2. **Saturday's parkrun (Aug 15) was a real near-max effort, not a controlled one.** 22:11 (7:07/mi), avg HR 188, max 201, mile splits climbing 174→192→195→198bpm — a positive split, essentially all-out. It didn't beat the 21:40 PB, which is useful: it corroborates that ~21:40-22:11 is genuinely where Josh's current 5K fitness sits, not something the model should assume is faster. But it's the **third straight week** "controlled" was the ask and a blowup was the result — the pacing-discipline limiter that gates the specific 1:42 target is trending backward, not forward.
3. **VO2max ticked back down to 57 today** (was 58, Aug 8-15) — after one week of no movement then a same-day dip. Most likely daily algorithm noise rather than a real fitness change, but it means there's no further VO2max-based case for raising the speed ceiling this cycle.
4. **Garmin's live HM prediction moved to 1:33:23** (from 1:34:57) — faster, so its optimism gap is discounted harder, not taken at face value (see below).

## Why not just use Garmin's own prediction?

Garmin live today (`get_race_predictions`, 2026-08-16): 5K **19:09** (1149s), 10K 41:07, **HM 1:33:23** (5603s), marathon 3:27:48.

Its 5K prediction is still faster than Josh's actual best-ever 5K (21:40 = 1300s, Jul 18 parkrun, real race effort) — and by a **wider** margin than last time: 1300/1149 = **+13.1% optimism** (was +11.6% on Aug 10, +8.3% on Aug 2). The gap keeps widening even as VO2max nudges around, which is more evidence the algorithmic number is decoupling from demonstrated race execution. Applying that same self-generated optimism ratio to today's HM number: 5603s × 1.13142 = **6340s = 1:45:40** — a "calibrated Garmin" figure, barely moved from Aug 10's 1:45:58.

## Speed ceiling (assumes race-adequate endurance — not there yet)

From actual best 5K (1300s, still the Jul 18 PB — Aug 15's 22:11 near-max effort corroborates this anchor rather than replacing it):
- **Riegel** (T2 = T1×(D2/D1)^1.06): 1300 × (21.0975/5)^1.06 = 1300 × 4.5998 = 5980s = **1:39:40** — still the known-optimistic outlier on a >4× distance extrapolation; upper bound, not the answer.
- **VDOT/Daniels**: 21:40 5K ≈ VDOT ~40-41 → HM ≈ **1:47:00-1:48:00** (unchanged, same anchor).
- **Calibrated Garmin**: **1:45:40**.

VDOT and calibrated-Garmin still cluster ~1:46-1:48; Riegel is still the outlier. No VO2max-based case to nudge this cycle (58→57 today). **Speed ceiling unchanged at ≈ 1:46:30 (6390s)**.

## Endurance-tax discount (measured, not assumed)

Evidence base, updated:
- **May 11 (13.5mi continuous, the injury run):** HR climbed 143→164bpm (+15%) at ~flat pace.
- **Jul 26 (6.0mi continuous):** HR climbed 149→185bpm (+24%) — worse decoupling, shorter distance.
- **Aug 10 (8.0mi walk-run, fresh legs):** ~0% net drift (lowest HR at the end).
- **Aug 16 (8.61mi walk-run, tired legs, LOW readiness):** mild ~11% rise (129→143bpm), stayed inside the Z2 ceiling throughout, under materially harder starting conditions than Aug 10.

Reading these together: durability keeps trending the right way (longer distance, harder starting state, still inside Z2), but Aug 16 wasn't a repeat of a perfectly flat trace — it's real but slightly weaker evidence than last cycle's "zero drift" framing implied. **Tax nudged down marginally to ~12%** (from 12.5%), crediting the tougher test passed while not overclaiming a fully flat result:

6390s × 1.12 = 7157s. **Smart-execution credit** (paced, tapered, fueled race vs. these training efforts, ~7%): 7157 × 0.93 = 6656s. **Course adjustment** (Ealing's ~140m rolling gain, ~+2min): +120s = 6776s.

**→ If raced today: ~1:53:00 (range 1:48-1:59).**

## If plan.md is followed to race day

`plan.md` v2 is unchanged since Aug 10 — long run still peaks at ~11.5mi (~88% of race distance), still re-centred on race-pace discipline. The arithmetic itself doesn't move:

- **Residual endurance tax by race day: ~3%** (unchanged — the 11.5mi peak logic hasn't changed).
- **Modest raw-speed gain: ~3%** (held, not increased — today's VO2max dip means no basis to raise this further, but a week of the number sitting at 58 before today's blip doesn't erase it either): 6390 × 0.97 = 6198s.
- **Residual tax applied:** 6198 × 1.03 = 6384s. **Course:** +120s = 6504s = **1:48:24**.
- **Adherence — the honest change this cycle.** Running-volume adherence stayed excellent (guardrails clean, long run executed as planned). But the *specific* adherence that matters most for the 1:42 target — pacing discipline — went **0-for-3** on "run it controlled" the last three weeks, and strength (the injury-insurance side) went 0-for-2 this week. Neither moves the arithmetic above directly, but both widen the honest uncertainty band: a plan followed on mileage but not on the discipline it's actually built around isn't full adherence.

**→ If plan v2 followed with realistic adherence: ~1:49:00 (range widened to 1:44-1:57, upper bound moved out to reflect the pacing-discipline risk).**

## Likelihood of hitting 1:42:00

Gap between the "if plan v2 followed" central estimate (1:49:00) and target (1:42:00) is **~7 minutes ≈ 6.4%** — essentially the same gap as Aug 10. But the composition changed: last cycle the gap was closing because the plan itself improved; this cycle the endurance side kept improving while the pacing side got worse, and those roughly offset. **This is the first snapshot where the number doesn't simply move toward the target** — worth naming rather than rounding away.

**→ ~17% (band ~13-21%)**, down a touch from ~18%. Still a real possibility, still a genuine stretch — the honest expected outcome sits around **1:49-1:53**, not 1:42. The single biggest lever remains the same as it's been: a continuous (not walk-run) long run holding flat HR at 8mi+ would be the strongest upgrade to the endurance-tax estimate. The second lever — pacing discipline — now needs an actual fix, not another data point in the wrong direction; next week's plan builds in a concrete mechanism (a 150bpm watch alert for parkrun mile 1) specifically because three weeks of just asking hasn't worked.

## What would move this number

- **A continuous long run (no walk breaks) holding flat HR at 8mi+** — still the single biggest lever, unchanged.
- **A genuinely controlled parkrun** — even just one, breaking the three-week pattern, would be real evidence the pacing mechanism (the HR alert) is working, not just a hope.
- Re-run after next week's quality session + controlled-parkrun attempt, and if VO2max moves decisively off the 57-58 range in either direction.
