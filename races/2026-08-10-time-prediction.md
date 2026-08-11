# Race Time Prediction — Ealing Half Marathon, snapshot 2026-08-10

_Built via /time-predicter | Target: 1:42:00 (locked 2026-07-20, re-confirmed 2026-08-10) | 48 days to race day (2026-09-27) | Supersedes `races/2026-08-02-time-prediction.md` | **Revised later on 2026-08-10 after the `plan.md` v2 rewrite** — the long run now peaks at ~11.5mi (was 9.9mi), which improves the "if plan followed" number (§"If plan.md is followed" below)._

## The three numbers

| | Time/likelihood | Range | vs. Aug 2 |
|---|---|---|---|
| **Likelihood of hitting 1:42:00** | **~18%** | ~15-22% | ▲ from ~12% |
| **If the race were run today** | **1:54:00** | 1:49-2:00 | ▲ from 1:56:00 |
| **If plan.md (v2) is followed (realistic adherence)** | **1:49:00** | 1:44-1:55 | ▲ from 1:52:00 |

**All three moved toward the target** since Aug 2 — a positive trajectory, driven by two things: the flat-HR 8-miler (evidence), and the `plan.md` v2 rewrite that raises the peak long run to ~11.5mi (a better plan closing more of the endurance gap). Still reasoned estimates from real formulas + Josh's data, not precise statistical output.

## What changed since Aug 2 (why the numbers moved)

1. **The Aug 10 long run: 8.0mi at avg 144bpm with essentially NO drift.** Running segments oscillated 146→139→153→151→150→147→154→152→145→135→146→**138bpm** — the *lowest reading was the final segment*, in 23-29°C heat. The last prediction named "closing the endurance-tax gap — the long run holding flat HR at progressively longer distances" as *the single biggest lever*. This is the first hard evidence of exactly that: a longer effort (8mi vs the prior 6mi) with less decoupling, not more.
2. **VO2max ticked 57 → 58** (Aug 8) — first movement in over a month of flat readings. Small, but it's real and it's the right direction.
3. **Garmin's live HM prediction rose to 1:34:57** (from 1:37:34) — noted, but its optimism gap *widened*, so it gets discounted harder, not taken at face value (see below).

**The honest caveat that keeps this from moving further:** the 8-miler was a **walk-run** (walk breaks throughout). Walk breaks reset HR and suppress drift — so the flat trace is partly strategy, not pure durability. A *continuous* 8mi would very likely still show some climb. It's strong positive evidence, but it is not yet proof of continuous-race durability at distance. He still has no continuous effort past ~6mi, and 13.1 continuous is unproven since the May injury run. That's why "if raced today" moves ~2min, not ~6.

## Why not just use Garmin's own prediction?

Garmin live today (`get_race_predictions`, 2026-08-10): 5K **19:25**, 10K 41:48, **HM 1:34:57**, marathon 3:29:55.

Its 5K prediction (19:25 = 1165s) is now **faster than Josh's actual best-ever 5K** (21:40 = 1300s, Jul 18 parkrun, real race effort, max HR 196) by an even wider margin than before: 1300/1165 = **+11.6% optimism** (was +8.3% on Aug 2) at the distance where fitness transfers most directly. Applying that same self-generated optimism ratio to its HM number: 5697s × 1.116 = **6358s = 1:45:58** — a "calibrated Garmin" figure, ~11 minutes slower than its raw output.

## Speed ceiling (assumes race-adequate endurance — not there yet)

From actual best 5K (1300s), three independent models:
- **Riegel** (T2 = T1×(D2/D1)^1.06): 1300 × (21.0975/5)^1.06 = 1300 × 4.599 = 5978s = **1:39:38** — known-optimistic on a >4× extrapolation without a proven endurance base; upper bound, not the answer.
- **VDOT/Daniels**: 21:40 5K ≈ VDOT ~40-41 → HM ≈ **1:47:00-1:48:00**.
- **Calibrated Garmin**: **1:45:58**.

VDOT and calibrated-Garmin cluster ~1:46-1:48; Riegel is the outlier. VO2max nudging to 58 supports the faster edge of that cluster very slightly. **Speed ceiling ≈ 1:46:30 (6390s)** — what he could run *if* he had race-adequate endurance depth at 13.1mi.

## Endurance-tax discount (measured, not assumed — and shrinking)

The tax is the durability gap between the speed ceiling and reality. Evidence base:
- **May 11 (13.5mi continuous, the injury run):** HR climbed 143→164bpm (+15%) at ~flat pace; the extracted HM segment = 2:03:28 @ avg 157.
- **Jul 26 (6.0mi continuous):** HR climbed 149→185bpm (+24%) at flat pace — worse decoupling, shorter distance.
- **Aug 10 (8.0mi walk-run):** ~0% net drift (lowest HR at the end) — but walk-run-assisted, so not directly comparable to the continuous efforts above.

The trend across these three (even discounting the walk-run) is a genuinely improving durability picture. Prior snapshot used a 15% tax off the continuous May effort. Revising **down to ~12.5%** for "if raced today" — crediting the demonstrated Z2 control and the 8mi effort, while holding back for the walk-run caveat and the unproven continuous 13.1:

6390s × 1.125 = 7189s. **Smart-execution credit** (a paced, tapered, fueled race vs. these uncontrolled/walk-run training efforts, ~7%): 7189 × 0.93 = 6686s = 1:51:26. **Course adjustment** (Ealing's ~140m rolling gain, ~+2min vs. the flat-course formulas): +120s = 6806s.

**→ If raced today: ~1:54:00 (range 1:49-2:00).**

## If plan.md is followed to race day

The rebuilt **`plan.md` v2 (2026-08-10)** targets this exact limiter harder than v1 did: the long run now peaks at **~11.5mi (~88% of race distance)**, up from v1's 9.9mi (76%), and the whole plan is re-centred on race-pace discipline (goal-pace calibration, negative-split long runs). Josh is also *ahead* of even the new schedule (already at 8mi). The long run still peaks a little below race distance, so a small residual tax remains — but less than before.

- **Residual endurance tax by race day: ~3%** (down from ~5% in the pre-rewrite estimate, and from the current ~12.5%) — the 11.5mi peak leaves far less unrehearsed distance, and race-pace-finish long runs specifically train the mile 10-11 zone. Taper/adrenaline covers the final ~1.5mi.
- **Modest raw-speed gain: ~3%** — more confident now VO2max has moved (57→58) rather than sat flat: 6390 × 0.97 = 6198s.
- **Residual tax applied:** 6198 × 1.03 = 6384s. **Course:** +120s = 6504s = **1:48:24**.
- **Adherence:** 5 weeks tracked, 2 disrupted (Jul 13 life/sleep, Jul 27 illness) — but the last two weeks were clean and strong with best-on-record recovery markers (HRV 89ms, ACWR optimal). Base rate improving; keep the central estimate near the clean-execution case, widen the range for honesty (a bigger build also carries slightly more disruption/injury risk, held in the range).

**→ If plan v2 followed with realistic adherence: ~1:49:00 (range 1:44-1:55).**

## Likelihood of hitting 1:42:00

Gap between the "if plan v2 followed" central estimate (1:49:00) and target (1:42:00) is now **~7 minutes ≈ 6-7% improvement beyond modeled expectation** (was ~9min / 8% pre-rewrite, ~10min / 9-10% on Aug 2). The gap keeps shrinking — mostly because the plan itself got better (higher peak long run), not because fitness jumped. Still a real ask, but more within reach of a good race day than it was.

**→ ~18% (band ~15-22%)** — trending the right way across all three snapshots. 1:42 is a genuine possibility if the long run keeps holding flat HR at growing distances (ideally *continuous*, not just walk-run), the race-pace discipline work lands, and late-September London stays cool. Honest read, still intact: **1:42:00 remains a stretch, not the expected outcome** — the expected outcome now sits around **1:49**, down from ~1:51. The single biggest lever remains executing the plan's long-run ramp with flat HR; the second is the pacing discipline that keeps race day from becoming the mile-10 fade the course is famous for.

## What would move this number (updated)

- **The single biggest lever, refined:** a *continuous* long run holding flat HR at 8mi+ — repeating today's flat trace without the walk breaks would be the strongest single upgrade to the endurance-tax estimate.
- A raced parkrun result faster than the 21:40 PB (Aug 15 is now a real effort — it would replace the aging Jul 18 anchor and could lift the whole speed ceiling).
- Re-run after Aug 15's parkrun, after the first Phase 2 quality block, and if VO2max moves again off 58.
