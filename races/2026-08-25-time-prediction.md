# Race Time Prediction — Ealing Half Marathon, snapshot 2026-08-25

_Built via /time-predicter | Target: 1:42:00 (locked 2026-07-20, re-confirmed 2026-08-10) | 33 days to race day (2026-09-27) | Supersedes `races/2026-08-16-time-prediction.md`_

## The three numbers

| | Time/likelihood | Range | vs. Aug 16 |
|---|---|---|---|
| **Likelihood of hitting 1:42:00** | **~20%** | ~15-25% | ▲ from ~17% — first genuine upward move in a while |
| **If the race were run today** | **~1:52:00** | 1:47-1:56 | ▲ from 1:53:00 |
| **If plan.md (v2) is followed (realistic adherence)** | **~1:48:30** | 1:44-1:54 | ▲ from 1:49:00, range narrowed |

**The best-news cycle in a month, and it's a real one, not a rounding artifact.** The pacing-discipline limiter — named the #1 problem on Aug 16 after going 0-for-3 on "run it controlled" — just had its strongest week yet: a genuine negative-split parkrun (Aug 22) and a deliberately-designed progression long run (Aug 24, longest on record at 9.01mi) that held its HR ceiling through 8 miles before a planned late push. That's the specific fix the Aug 16 snapshot said was needed, landing. Combined with a small further durability nudge, both headline numbers move the right way for the first time in three snapshots.

## What changed since Aug 16 (why the numbers moved)

1. **Saturday Aug 22 parkrun: a genuine negative split, breaking the 3-week bad-pacing streak.** 3.12mi, 9:09 → 7:54 → 7:24 → ~6:01/mi, avg HR 170, max 194. HR climbing alongside pace is exactly what a well-executed negative split looks like. This is the first parkrun since the "leash came off" (Aug 8) that wasn't a blow-up — direct evidence the standing 150bpm-alert mechanism is working, not just a hope.
2. **Monday Aug 24 long run: 9.01mi, avg 142bpm — longest run on record, and a designed progression, not a flat consolidation.** Mile-by-mile HR: 132→135→137→142→143→145→149→146→153bpm. The body of the run (miles 1-8) stayed at or under a ~150bpm ceiling; only the final mile pushed to 153, on purpose, per that week's plan (`training/2026-08-17-week.md`). This is a *different* — and arguably more race-specific — kind of evidence than Aug 16's passive drift-under-fatigue test: it shows active pace/effort control extending to mile 8-9, which is literally the mile 10-11 skill the race demands. It is not, however, a repeat of a perfectly flat trace, so the endurance-tax discount below moves only modestly, not sharply.
3. **Both guardrails held with real margin.** Long run +4.6% vs the 10% cap (baseline 8.61mi → 9.01mi actual); weekly volume +14.2% vs the 30% cap. Strength went 3-for-3, the first full week since consistency started slipping.
4. **VO2max still flat, 57-58 range** (57.0 on Aug 24, per `get_vo2max_trend`) — no new basis to raise the speed ceiling or the raw-speed-gain assumption this cycle.
5. **Garmin's live HM prediction moved to 1:35:27** (from 1:33:23 on Aug 16) — slower, not faster, and its optimism gap versus Josh's actual 5K PB narrowed too (see below). Read together with the 5K prediction also slowing (19:09 → 19:26), Garmin's algorithm is recalibrating a little closer to reality, not drifting further from it.

## Why not just use Garmin's own prediction?

Garmin live today (`get_race_predictions`, 2026-08-25): 5K **19:26** (1166s), 10K 41:53, **HM 1:35:27** (5727s), marathon 3:32:19.

Its 5K prediction is still faster than Josh's actual best-ever 5K (21:40 = 1300s, Jul 18 parkrun, real race effort, corroborated by the Aug 15 all-out 22:11 near-max effort) — but the gap **narrowed** this cycle: 1300/1166 = **+11.5% optimism** (was +13.1% on Aug 16, +11.6% on Aug 10, +8.3% on Aug 2). First narrowing after two straight widenings — treat as a data point, not a confirmed reversal. Applying that same self-generated optimism ratio to today's HM number: 5727s × 1.1149 = **6385s = 1:46:25** — the "calibrated Garmin" figure, essentially flat versus Aug 16's 1:45:40.

## Speed ceiling (assumes race-adequate endurance — not there yet)

From actual best 5K (1300s, still the Jul 18 PB — no new race effort this cycle):
- **Riegel** (T2 = T1×(D2/D1)^1.06): 1300 × (21.0975/5)^1.06 = 1300 × 4.5998 = 5980s = **1:39:40** — still the known-optimistic outlier on a >4× distance extrapolation; upper bound, not the answer.
- **VDOT/Daniels**: 21:40 5K ≈ VDOT ~40-41 → HM ≈ **1:47:00-1:48:00** (unchanged, same anchor).
- **Calibrated Garmin**: **1:46:25**.

VDOT and calibrated-Garmin still cluster ~1:46-1:48; Riegel is still the outlier. No VO2max-based case to move this cycle (57.0 on Aug 24, same flat range it's held since early August). **Speed ceiling essentially unchanged at ≈ 1:46:40 (6400s)**.

## Endurance-tax discount (measured, not assumed)

Evidence base, updated:
- **May 11 (13.5mi continuous, the injury run):** HR climbed 143→164bpm (+15%) — involuntary decoupling.
- **Jul 26 (6.0mi continuous):** HR climbed 149→185bpm (+24%) — worse decoupling, shorter distance.
- **Aug 10 (8.0mi walk-run, fresh legs):** ~0% net drift.
- **Aug 16 (8.61mi walk-run, tired legs, LOW readiness):** mild ~11% rise (129→143bpm), stayed inside the Z2 ceiling.
- **Aug 24 (9.01mi, MODERATE readiness, designed progression run):** 132→153bpm across the run, but miles 1-8 all sat at or under a ~150bpm self-imposed ceiling (132/135/137/142/143/145/149/146), with the rise to 153 confined to a deliberate final-mile push per that week's plan. Longest continuous distance on record.

Reading these together: this is a different category of evidence than the passive-drift tests above — it's active, planned effort control extending to mile 8-9, not absence of involuntary decoupling. That's arguably more directly informative for race durability (the mile 10-11 fade is exactly a failure of controlled effort, not just aerobic capacity), but it isn't a repeat of Aug 10's flat trace either, so the discount moves modestly rather than sharply. **Tax nudged down to ~10.5%** (from 12%):

6400s × 1.105 = 7072s. **Smart-execution credit** (paced, tapered, fueled race vs. these training efforts, ~7%): 7072 × 0.93 = 6577s. **Course adjustment** (Ealing's ~140m rolling gain, ~+2min): +120s = 6697s.

**→ If raced today: ~1:52:00 (range 1:47-1:56).**

## If plan.md is followed to race day

`plan.md` v2 is unchanged since Aug 10 — long run still peaks at ~11.5mi (~88% of race distance), still re-centred on race-pace discipline. The arithmetic:

- **Residual endurance tax by race day: ~3%** (unchanged — the 11.5mi peak logic hasn't changed).
- **Modest raw-speed gain: ~3%** (held — VO2max still flat at 57-58, no basis to raise this further): 6400 × 0.97 = 6208s.
- **Residual tax applied:** 6208 × 1.03 = 6394s. **Course:** +120s = 6514s = **1:48:34**.
- **Adherence — the genuinely good news this cycle.** The specific gap flagged on Aug 16 (pacing discipline going 0-for-3, widening the uncertainty band) got its first real fix: a negative-split parkrun and a controlled-to-mile-8 long run in the same week, plus 3-for-3 strength and both guardrails held clean. This doesn't change the mileage-based arithmetic above directly, but it removes the specific reason the range was widened last cycle — one strong week isn't proof of a durable pattern, so the range narrows partway back, not all the way.

**→ If plan v2 followed with realistic adherence: ~1:48:30 (range narrowed to 1:44-1:54).**

## Likelihood of hitting 1:42:00

Gap between the "if plan v2 followed" central estimate (1:48:30) and target (1:42:00) is **~6.5 minutes ≈ 6.4%** — a touch smaller than Aug 16's ~7min/6.9% gap. The bigger change is qualitative: last cycle's biggest risk (pacing discipline actively trending backward) just produced its best data point yet, which is worth more than the raw arithmetic move alone.

**→ ~20% (band ~15-25%)**, up from ~17%. Still the honest expected outcome sits around **1:48-1:52**, not 1:42 — this remains a genuine stretch, not a coin flip. But this is the first snapshot where both the qualitative story and the numbers moved toward the target at the same time. One good week doesn't erase three shaky ones — the next 1-2 snapshots need to show the negative-split parkrun and controlled long run were the new normal, not a one-off, before this trend gets more credit than it's currently given.

## What would move this number

- **A repeat of Aug 22/24's execution** — another controlled parkrun and another long run holding ceiling deep into the distance — would be the strongest possible confirmation that the pacing fix is real, not a one-off.
- **A continuous (no walk-run) long run holding flat HR at 9mi+** would still sharpen the endurance-tax estimate further, distance permitting under the guardrails.
- Re-run after this week's quality session (Wed Aug 26) + parkrun (Sat Aug 29) + the Aug 31 long run, and immediately if VO2max moves decisively off the 57-58 range.
