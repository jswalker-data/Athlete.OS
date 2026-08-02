# Race Time Prediction — Ealing Half Marathon, snapshot 2026-08-02

_Built via /time-predicter | Target: 1:42:00 (locked 2026-07-20) | 56 days to race day (2026-09-27)_

## The three numbers

| | Time/likelihood | Range |
|---|---|---|
| **Likelihood of hitting 1:42:00** | **~12%** | ~10-15% |
| **If the race were run today** | **1:56:00** | 1:50-2:05 |
| **If plan.md is followed (realistic adherence) to race day** | **1:52:00** | 1:46-2:00 |

These are reasoned estimates from real formulas and Josh's actual data — not a precise statistical output. Full arithmetic below.

## Why not just use Garmin's own prediction?

Garmin's live algorithmic prediction today (`get_race_predictions`, 2026-08-02): 5K 20:00, 10K 43:09, **HM 1:37:34**, marathon 3:35:29.

`athlete-profile.md` already flags this as an optimistic ceiling, not a target — and there's a concrete, quotable reason why: Garmin's own live 5K prediction (20:00 = 1200s) is **faster than Josh's actual best-ever 5K** (21:40 = 1300s, Jul 18 parkrun, a genuine race effort, max HR 196). Garmin's model thinks he could beat his own PB by 100 seconds *right now*, at the distance where fitness transfers most directly and endurance-depth matters least. That's a measurable **8.33% optimism gap** (1300/1200 = 1.0833) at the easiest case. The longer the distance, the more the model's assumption of trained fatigue-resistance matters — and per his own ranked limiters, aerobic efficiency and long-run ceiling (not raw speed) are exactly where Josh is weakest. Applying Garmin's own demonstrated optimism ratio to its HM prediction: 5854s × 1.0833 = **6341s = 1:45:41** — a "calibrated Garmin" estimate, and already 8 minutes slower than its raw output.

## Building the "speed ceiling" (assumes adequate endurance base — he doesn't have one yet)

Three independent models from the actual best 5K (1300s):

- **Riegel** (T2 = T1×(D2/D1)^1.06): (21.0975/5)^1.06 = 4.599 → 1300×4.599 = 5978s = **1:39:38**. Riegel is known to run optimistic on >4x distance extrapolations without a demonstrated endurance base at the target distance — treat as an upper bound, not the answer.
- **VDOT/Daniels table cross-check**: 21:40 5K ≈ VDOT ~40-41 → table-equivalent HM ≈ **1:47:00-1:48:00**.
- **Calibrated Garmin** (above): **1:45:41**.

VDOT and calibrated-Garmin cluster tightly (~1:46-1:48); Riegel is the outlier for the reason stated. Weighted toward the VDOT/calibrated cluster: **speed ceiling ≈ 1:47:00 (6420s)** — what he could run *if* he already had race-adequate endurance depth at 13.1 miles.

## The endurance-tax discount (he doesn't have that depth yet — this is measured, not assumed)

Two real data points, both showing genuine aerobic decoupling (HR climbing while pace holds or increases — not just fatigue, a specific durability gap):

- **Jul 26, 2026 (in-block, 6.0mi)**: mile splits ~9:03/8:39/8:44/8:53/8:50/8:44 (flat-to-faster pace) while HR climbed **149→160→174→179→181→183→185bpm** — a +36bpm (+24%) rise over just 6 miles at unchanged effort.
- **May 11, 2026 (pre-block, 13.5mi, the run that caused the knee injury)**: HR climbed **143→164bpm (+15%)** over the full distance at a roughly flat ~9:20-9:30/mi pace throughout (the extracted "half marathon PR" segment from this run: 2:03:28 at avg HR 157).

Using the more race-distance-relevant number (~15%, from the actual 13.5mi effort) as the tax: 6420s × 1.15 = **7383s (2:03:03)**.

**This converges almost exactly with his actual demonstrated 2:03:28** from the May run — strong evidence the methodology is grounded correctly, not just theoretical.

**Smart-execution credit**: the May run was an uncontrolled training effort (not a paced race, and it's the run that caused the injury) — a properly paced, tapered, fueled race effort today should improve on that raw number by roughly 6-8% through pacing discipline alone, independent of any fitness gain. 7383s × 0.93 ≈ 6866s = 1:54:26.

**Course adjustment**: Ealing's ~140m rolling elevation gain costs a real few minutes versus the flat-course assumption baked into all the formulas above. Adding ~2min: 6986s ≈ **1:56:26**.

**→ If raced today: ~1:56:00 (range 1:50-2:05).**

## If plan.md is followed to race day

`plan.md`'s remaining phases (Build → Peak → Taper) are specifically aimed at this exact limiter: long run progressively grows from this week's ~4.8mi to a peak of 9.9mi (Week 7), and one quality session/week returns from Phase 2 (Week 4, Aug 17). The long run deliberately peaks at ~76% of race distance, not 100% — `plan.md` itself already names taper freshness/adrenaline as covering the rest, so some residual endurance tax legitimately remains on race day even with clean execution.

- **Residual endurance tax by race day**: estimate shrinking from the current ~15% to **~5%**, reflecting a properly built (if not full-distance) long run and demonstrated Z2 discipline (Aug 1-2 this week: 133bpm and 141bpm avg HR, both genuinely Z2 — the best two-session stretch on record for this specific gap).
- **Modest raw-speed gain**: VO2max has been flat at 57 for over a month, so this stays conservative — ~2-3% off the speed ceiling from ~5 weeks of weekly quality sessions in Phase 2-3. 6420s × 0.975 ≈ 6260s.
- **Adherence discount**: of the 4 weeks tracked since late June, 2 had significant disruptions (Jul 13 life/sleep, Jul 27 illness) — a real ~50% base rate for disruption, but both were well-managed with fast HRV bounce-back and no compounding fitness loss (per `reviews/`). This argues for keeping the central estimate close to the "clean execution" case rather than a heavy penalty, while widening the range to reflect real uncertainty.

Combined: 6260s × 1.05 (residual tax) = 6573s, + course adjustment (~2min) = 6693s ≈ **1:51:33**.

**→ If plan followed with realistic adherence: ~1:52:00 (range 1:46-2:00).**

## Likelihood of hitting 1:42:00

The gap between the "if plan followed" central estimate (1:52:00) and the target (1:42:00) is **10 minutes — roughly a 9-10% improvement beyond the modeled expectation**, needed in a single race-day performance. That's a bigger ask than typical race-day variance for a recreational runner with limited race experience (a few-percent PB-day outperformance is plausible; ~10% faster than modeled expectation is tail territory, not a coin flip).

**→ ~12% (band: ~10-15%)** — a real chance if training executes cleanly, pacing is disciplined (negative-split, not going out too hot), and race-day conditions are favorable (per the dossier, cool London late-September mornings are the likely case) — but the honest read is that 1:42:00 is currently a stretch goal, not the expected outcome. `athlete-profile.md` already names sub-1:30 as stretch/upside; this analysis suggests 1:42:00 itself now sits closer to that stretch territory than "realistic base plan," given where the endurance-depth data actually is today.

## What would move this number

- **The single biggest lever**: closing the endurance-tax gap faster than modeled — i.e., the long run holding flat HR/pace (like Aug 2's 141-145bpm-flat effort) at progressively longer distances over the coming weeks, not just at today's ~4-5mi range.
- Re-run this after each new long run PR, after the first quality session block (Phase 2, Aug 17+), and immediately if VO2max actually moves off 57.
- A clean run to the 9.9mi peak long run (Week 7, Sep 7-13) with flat HR the whole way would be the strongest single piece of evidence to revise this upward.
