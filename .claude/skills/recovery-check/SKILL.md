---
name: recovery-check
description: Daily readiness and injury-risk check for Josh — pulls his recent training load and health factors from Garmin, computes his own acute:chronic workload ratio (not a generic threshold), weighs in what he actually tracks (Garmin only), flags early overtraining/injury-risk markers, and gives a simple readiness call (go hard / go easy / rest) with the reason and evidence. Saves notable flags to health/ with a date; stays quiet on normal days. Use when Josh asks "am I good to train today", "readiness check", "should I go hard today", or runs /recovery-check — including the automatic morning run.
---

# /recovery-check — daily readiness and injury-risk check

This is the daily companion to `/weekly-review` and `/plan-my-week`: a fast,
same-day read on whether today's planned effort is safe, not a retrospective.
It exists because CLAUDE.md's hard rule — always flag overtraining/injury risk
directly, and respect Josh's injury history — needs a daily trigger, not just
a weekly one. Keep it **signal, not noise**: most mornings the honest answer
is "nothing's wrong, go do the plan," and it should say that briefly and stop,
not manufacture concern to justify running.

## The science this is built on

These are load-bearing, not decoration — apply them, don't just cite them.

**1. Acute:Chronic Workload Ratio (ACWR) — the load side.** ACWR compares a
short-term "acute" load (commonly a 7-day window) against a longer "chronic"
load (commonly 28 days) as a proxy for whether recent training has spiked
relative to what the body is actually adapted to. The commonly cited "sweet
spot" is **0.8–1.3**; risk rises sharply above **1.5**, and very low ratios
(well under 0.8, chronic underloading) aren't risk-free either — they usually
just mean detraining, not injury. In elite cricket/team-sport data, an ACWR
above 2 has been associated with 2-4x the injury risk of the sweet-spot band.
([Science for Sport: ACWR](https://www.scienceforsport.com/acutechronic-workload-ratio/),
[PubMed: ACWR systematic review](https://pubmed.ncbi.nlm.nih.gov/32572824/),
[Dove Press: ACWR and injury risk](https://www.dovepress.com/the-relationship-between-acute-chronic-workload-ratios-and-injury-risk-peer-reviewed-fulltext-article-OAJSM))
**Important caveat:** ACWR's methodology has real, published problems —
mathematical coupling between the acute and chronic terms, sensitivity to
which calculation method (rolling average vs. EWMA) is used, and a lack of
clear causal evidence (Impellizzeri and colleagues have gone as far as
requesting corrections to widely-reused ACWR illustrations). Treat the ratio
as a **directional heuristic to cross-check against other signals**, never as
a precise, standalone predictor.
([Impellizzeri: Conceptual Issues and Fundamental Pitfalls](https://www.researchgate.net/publication/341936245_AcuteChronic_Workload_Ratio_Conceptual_Issues_and_Fundamental_Pitfalls),
[Global Performance Insights: Has ACWR Been Debunked?](https://www.globalperformanceinsights.com/post/has-the-acute-chronic-workload-ratio-been-debunked))
→ **Applied here:** compute ACWR from Josh's **own rolling load history**
(`get_training_load_trend`), never a fixed generic mileage number — this
matches how `/plan-my-week` already treats the volume guardrails. Specifically watch
for a **low base followed by rapid resumption** (a gap of several days, then
training on 3+ consecutive days, or jumping straight back to prior volume) —
this is Josh's own named overreach pattern and the exact mechanism behind his
May 2026 13.5-mile knee injury. Flag this explicitly even when the raw ratio
still reads "moderate," since a short baseline window can mask a real spike.

**2. HRV and resting heart rate (RHR) trends.** A falling HRV combined with a
rising RHR is the classic sympathetic "alarm response" to accumulating
fatigue — the standard signal used to guide endurance training load day to
day. But it isn't perfectly reliable in one direction: several studies have
found HRV can paradoxically **rise** in some overtrained endurance athletes
rather than fall, so trend and context matter more than a single day's
number, and HRV alone is best paired with RHR, training load, and sleep
rather than read in isolation.
([SimpliFaster: Interpreting HRV Trends](https://simplifaster.com/articles/interpreting-hrv-trends-athletes/),
[Science for Sport: HRV](https://www.scienceforsport.com/heart-rate-variability-hrv/),
[PMC: Monitoring Training and Recovery in Recreational Endurance Athletes](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7967764/))
On RHR specifically: a sustained elevation of **5-10bpm above an athlete's own
morning baseline for 3+ consecutive days** is a strong physiological signal of
non-functional overreaching, early overtraining, or incoming illness — the
duration matters as much as the size of the jump.
([RunnersConnect: Fatigue, Illness, Overtraining and RHR](https://runnersconnect.net/overtraining-resting-heart-rate/),
[TrainingPeaks: The 4 Signs of Overtraining](https://www.trainingpeaks.com/coach-blog/the-4-signs-of-overtraining/))
→ **Applied here:** build Josh's **own personal RHR baseline** from his last
~10-14 days (he has no independent tracking outside Garmin — see below — so
Garmin's own numbers are the entire signal, and trend integrity matters more
than any single reading). Cross-check against `get_hrv_trend`'s own guidance
(>10ms drop from the 7-day rolling baseline is its flag threshold) rather than
inventing a separate one.

**3. Early markers of overtraining (Meeusen et al., ECSS/ACSM joint consensus,
2013).** Overtraining exists on a spectrum: functional overreaching (FOR,
recovers in days — the normal cost of a hard training block), non-functional
overreaching (NFOR, recovery takes weeks to months), and true overtraining
syndrome (OTS, months). No single marker — hormonal, performance, or
psychological — reliably distinguishes these on its own; the field's own
consensus is that **prolonged maladaptation across a cluster of markers** is
the real signal, not any one soft flag in isolation. The markers worth
watching day to day: unexplained performance decrement despite steady or
increased effort, mood/motivation disturbance, persistent fatigue, sleep
disturbance, elevated RHR, and suppressed or erratic HRV.
([Meeusen et al. 2013, European Journal of Sport Science](https://onlinelibrary.wiley.com/doi/10.1080/17461391.2012.730061),
[full text PDF](https://www.sportgeneeskunde.com/wp-content/uploads/Meeusen-et-al-2013-Overtraining-Consensus-ECSS-ACSM.pdf))
→ **Applied here:** the real flag threshold is **2 or more markers
co-occurring** in the same window, not any single soft signal alone — this is
what keeps the check quiet on normal days and only speaks up when something
is actually converging.

## What Josh told us this shapes on top of the science

(Captured 2026-07-26 via direct interview; re-confirm if it's been a long
time or life has clearly changed.)

- **Sleep:** wears the watch every night, and Garmin's score generally
  matches how he actually feels — **but** Garmin's sleep session cuts off
  early on mornings he wakes around 5-6am and then dozes for roughly another
  hour that never gets tracked. **Don't auto-flag a borderline/short sleep
  score in isolation.** If a "go easy" or "rest" call would hinge mainly on a
  marginal sleep number, ask Josh directly whether it was a genuinely short
  night or the early-wake-then-doze pattern before finalizing the call.
- **HRV/RHR:** Garmin only — no other device, no independent personal
  tracking or baseline sense of his own. Garmin's own numbers and trend tools
  **are** the complete signal here; there's nothing external to reconcile
  against, so lean on `get_hrv_trend` and the RHR baseline computed from his
  own history rather than looking for a second opinion that doesn't exist.
- **Life stress:** chronically **high baseline**, not an occasional spike —
  demanding work (data/AI consultant, platform engineering for banks) plus a
  busy personal life right now (as of 2026-07-26). **Don't flag "elevated
  stress" as new information on its own** — Garmin's stress score running
  moderate-high is close to his normal. Watch instead for stress climbing
  meaningfully **above** that already-elevated baseline, or for stress
  compounding with poor sleep or suppressed HRV on the same days — that
  combination is the actual signal, not the baseline level itself.
- **Overreach pattern:** stacking hard days back-to-back, and specifically
  **ramping straight back into daily training immediately after any gap** —
  Josh's own words: "after a patch off I sometimes try to then go out every
  day." This is his self-identified failure pattern and the direct mechanism
  behind the May 2026 13.5-mile injury. **This is the single highest-priority
  personalized flag**: whenever recent activity history shows a training gap
  of 4+ days followed by resumption on 3+ consecutive days (or an immediate
  jump back to pre-gap volume), flag it explicitly regardless of what the raw
  ACWR ratio says that day — the ratio's short baseline window can hide
  exactly this pattern.

## Process

### 1. Read standing context
- `athlete-profile.md` — zones, injury history (knee/hip), hard rules.
- `training/plan.md` (current phase) and the most recent
  `training/<Monday>-week.md` — what's actually scheduled for today, so the
  readiness call has something concrete to clear or downgrade.
- List `health/` and read the most recent 2-3 flagged entries, if any exist —
  today's read should be checked against a trend, not judged alone (mirrors
  how `/weekly-review` reads past reviews first).

### 2. Pull today's + trailing data from Garmin
- `get_training_readiness` / `get_morning_training_readiness` (today) —
  Garmin's own composite score and factor breakdown; the fastest single
  signal and a good sanity check against everything computed below.
- `get_training_load_trend`, last 35-42 days — CTL/ATL/TSB/ACWR computed from
  Josh's actual history, not an assumed baseline.
- `get_activities_by_date`, last 21 days — to directly detect the
  gap-then-stack pattern (don't just infer it from the ratio).
- `get_hrv_trend`, last 14-21 days.
- `get_heart_rates_summary`, last ~10 days (one call per day) — build a
  personal RHR baseline (rolling average) and compare today's value and any
  elevation streak against it.
- `get_sleep_summary`, last night plus the trailing week — flag anything that
  might be the early-wake-then-doze underestimate rather than a true short
  night (see above).
- `get_stress_summary` or `get_all_day_stress`, today plus the trailing week.
- `get_body_battery`, today plus the last few days.

### 3. Compute and assess
Build a short internal picture (this doesn't need to all be shown to Josh):
- ACWR today and its band (sweet spot / high / low), plus the gap-then-stack
  check.
- HRV vs. its own 7-day baseline (flag if down >10ms).
- RHR vs. Josh's own rolling baseline, and how many consecutive days it's
  been elevated.
- Sleep, with the early-wake caveat applied — don't count a night as short
  without considering it.
- Stress vs. Josh's own elevated normal, not an absolute scale.
- Garmin's own readiness score and which factors it names as weak.
- **Count how many distinct markers are actually flagged** — per Meeusen,
  the threshold that matters is 2+ co-occurring, not one soft signal.

### 4. Make the readiness call
Exactly three possible calls: **Go hard**, **Go easy**, or **Rest**. State
the call, the primary reason in 1-2 sentences, and the specific evidence
behind it (real numbers/dates, not vague language) — not a full data dump.
Weigh the call against what's already scheduled today per the week file
(e.g. if today's already a rest day, say whether the data agrees or would
have called it anyway). **Joint pain — known or newly reported — overrides
every other metric and means Rest, full stop, no negotiation**, per the
CLAUDE.md hard rule and Josh's injury history.

**Running unattended (the scheduled morning run):** if the call genuinely
hinges on something that would normally warrant asking Josh directly (a
borderline sleep score that might be the early-wake-then-doze pattern, an
ambiguous stress reading), default to the **more conservative call** ("go
easy" over "go hard"), name the ambiguity plainly in the write-up, and ask
the actual question the next time Josh is in a live conversation rather than
guessing silently.

### 5. Decide whether to write to health/
Default: **say nothing further, don't create a file.** A normal day clearing
the plan is not a filing event — this is the "signal, not noise" rule in
practice.
Write only when there's a genuine flag: an overtraining-marker cluster (2+
per step 3), a real ACWR spike (>1.5) or the gap-then-stack pattern, an RHR
elevation sustained 2+ mornings, joint pain, or a real trend break worth
remembering later. Save to `health/<date>.md` (ISO date, e.g.
`health/2026-07-26.md`). **Never overwrite a past entry** — a new dated file
each time a flag fires, same convention as `reviews/`.

### 6. Report
Keep the daily message short: the call, the reason, and (only if applicable)
the flag and what to do about it. Don't restate every number that was
pulled — the full picture belongs in the saved file on flag days, not in the
everyday conversation. Tone: direct, accountability not flattery, per
`athlete-profile.md` — say plainly when something's wrong, and say plainly
when everything's genuinely fine, without padding either one.
