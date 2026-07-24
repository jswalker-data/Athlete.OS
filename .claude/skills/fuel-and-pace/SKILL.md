---
name: fuel-and-pace
description: Build Josh a race-day fueling and pacing plan — carbs/hr, fluid/hr, sodium/hr and exactly when to take them, plus a pace-by-segment plan adjusted for elevation, altitude, and conditions. Grounded in real exercise-science limits (carbohydrate oxidation ceilings, glucose-fructose co-ingestion, sweat-rate/sodium physiology, heat and altitude effects), Josh's actual inputs where he has them, and clearly labeled estimates where he doesn't. Reads the race dossier in races/ and athlete-profile.md, asks what Josh knows, estimates the rest with a one-line "how to measure this for real" note, shows all the math, and flags anything at a physiological limit. Saves to fueling-pace/. Use when Josh asks to "plan my fueling", "build a race plan", "how should I pace/fuel [race]", or runs /fuel-and-pace.
---

# /fuel-and-pace — race-day fueling and pacing plan

A fueling and pacing plan is only as good as the physiology it's built on.
This skill exists so every number in Josh's race plan traces back to either
his own measured data or a clearly labeled estimate — never a guess dressed
up as a fact. Never stall waiting on a number Josh doesn't have: estimate it
from his body weight and the race conditions, label it, tell him how to
measure the real thing later, and move on.

## The science this is built on

Cite these when explaining the plan, not just in this file. If new research
changes a number materially, update this section and say what changed.

**Carbohydrate oxidation has a hard ceiling, and it depends on what you eat.**
A single carbohydrate source (glucose/maltodextrin alone) is capped at
roughly **60 g/hr** — the intestinal SGLT1 transporter that absorbs glucose
saturates above that rate, so more intake just sits in the gut and causes
distress rather than getting oxidized. Glucose and fructose use *different*
intestinal transporters (SGLT1 and GLUT5), so a glucose:fructose blend
("multiple transportable carbohydrates") raises the ceiling to **90 g/hr+**,
in some trials as high as 105-120 g/hr.
([Jeukendrup, GSSI — Multiple Transportable Carbohydrates](https://www.gssiweb.org/sports-science-exchange/article/sse-108-multiple-transportable-carbohydrates-and-their-benefits);
[Jeukendrup 2010, PubMed](https://pubmed.ncbi.nlm.nih.gov/23765351/);
[O'Brien et al., combined fructose-maltodextrin at 90 vs 120 g/h](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9560939/))

**How much carbohydrate depends on duration** (IOC/ACSM consensus):
- Under 45 min: no carbohydrate intake needed.
- 45-75 min: small amounts, or a mouth rinse only.
- 1-2.5 hr: **30-60 g/hr**, single-source carbs are fine at this rate.
- Over 2.5-3 hr: **up to 90 g/hr**, which requires a glucose:fructose blend
  since single-source carbs cap out well below that.
([IOC Consensus Statement on Sports Nutrition](https://stillmed.olympic.org/media/Document%20Library/OlympicOrg/IOC/Who-We-Are/Commissions/Medical-and-Scientific-Commission/EN-IOC-Consensus-Statement-on-Sports-Nutrition-2010.pdf);
[Kerksick et al., personalized carbohydrate intake](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4008807/))

**The real ceiling for most athletes is gut tolerance, not oxidation
capacity.** An untrained gut can't absorb 90 g/hr even though the transporter
math says it's possible — it needs to be trained. Practicing carb intake
during long training sessions (starting at 30-40 g/hr on runs 90+ minutes)
cuts GI symptoms by 60-63% within two weeks, and 6-8 weeks of consistent
practice typically lifts tolerance from ~45 g/hr toward 90+ g/hr. This is why
the plan always asks what Josh's gut is actually trained to handle before
assuming the physiological ceiling is usable.
([RunnersConnect gut-training guide, citing Stellingwerff & Cox](https://runnersconnect.net/gut-training-guide/);
[Gut-training systematic review, PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC10185635/))

**Fluid needs come from sweat rate, not a fixed number.** Sweat rate varies
roughly 0.5-2.0 L/hr between individuals and rises with pace, heat, and
humidity. The goal is to keep body-mass loss during exercise under **2%**
(ACSM) — under-replacing that much starts to cost performance and
heat-tolerance; over-replacing risks hyponatremia. Gut absorption itself caps
around **1.0-1.2 L/hr**, so a very high sweat rate (>1.2 L/hr) can't be fully
replaced during exercise no matter how much is drunk — that gap has to be
accepted, not fought.
([ACSM Position Stand: Exercise and Fluid Replacement](https://www.researchgate.net/publication/232208129_ACSM_Position_Stand_Exercise_and_Fluid_Replacement);
[Korey Stringer Institute — Hydration](https://koreystringer.institute.uconn.edu/hydration/))

**Sweat sodium concentration varies enormously between people** — roughly
460-1840 mg/L, averaging ~950 mg/L, and it climbs with exercise intensity
(≈700 mg/L at low intensity, ≈940 at moderate, ≈1130 at high). This is the
single most individual number in the whole plan: two athletes with the same
sweat rate can have a 3-4x difference in sodium loss. Self-reported "salty
sweater" signs (visible white salt stains on kit/skin, sweat that stings the
eyes or tastes strongly salty, salt crusting) reliably track toward the
higher end of that range.
([Sweat electrolyte losses, exercise intensity, PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6373370/);
[Interindividual variability in sweat sodium, marathoners, PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4966593/))

**Altitude changes both fluid and carb needs, but only above ~1500-2000m.**
Lower humidity plus a hypoxia-driven increase in ventilation and diuresis
raise fluid losses at altitude, and carbohydrate reliance increases as
altitude climbs (more anaerobic contribution, faster glycogen use). Below
that threshold (roughly sea level to 1600m), guidance mirrors sea level —
don't invent an altitude adjustment for a low-elevation course.
([Nutrition and Altitude, narrative review, PMC](https://pmc.ncbi.nlm.nih.gov/articles/PMC6901429/);
[Exogenous glucose oxidation in hypoxia, PMC](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7354086/))

**Heat slows pace, predictably.** Marathon finishing time slows by roughly
**1-2 minutes per °C** above the thermally ideal band of ~8-15°C (46-59°F);
below and within that band, temperature isn't a meaningful drag on pace.
Effect scales with race duration (a 5k loses much less absolute time than a
marathon for the same °C) and is a bit larger for faster/fitter runners in
absolute pace terms, though slower runners are exposed to the heat for
longer. Translate this to Josh's race duration proportionally, don't apply
the marathon-sized number to a shorter race.
([Effect of ambient temperature on marathon pacing, PubMed](https://pubmed.ncbi.nlm.nih.gov/18685522/);
[Running Writings — heat and humidity vs marathon time](https://runningwritings.com/2025/04/heat-humidity-marathon-times.html))

**Elevation changes effort, not just distance — use grade-adjusted pace.**
The energy cost of running at a given grade, relative to flat ground, follows
Minetti's polynomial: `cost_ratio(g) = (155.4g⁵ − 30.4g⁴ − 43.3g³ + 46.3g² +
19.5g + 3.6) / 3.6`, where `g` is grade as a decimal (0.05 = 5% uphill,
negative for downhill). Roughly: a 5% grade costs ~1.3x flat effort, 10%
costs ~1.66x, 15% costs ~2.06x; downhill is easier until it gets steep
(~15-20%+), where braking/eccentric load makes it costly again. Use this to
convert a flat target pace into a real per-segment pace given the course's
elevation profile, rather than pretending the course is flat.
([Grade-Adjusted Pace calculator and Minetti derivation, Running Writings](https://apps.runningwritings.com/gap-calculator/);
[Fellrnr — Grade Adjusted Pace](https://fellrnr.com/wiki/Grade_Adjusted_Pace))

## Process

### 1. Read the standing context
- `athlete-profile.md` — get body weight. If it's not there, ask Josh
  directly rather than guessing (a body-weight guess corrupts every formula
  downstream). It's also fine to check Garmin body composition/weigh-in data
  as a quick cross-check if profile weight looks stale — `CLAUDE.md` treats
  Garmin as the source of truth for training data (read-only), so use it as a cross-check rather than a persisted reference.
- The race dossier in `races/` for the target race (default to the goal
  race in `athlete-profile.md` if Josh doesn't name one; ask if neither
  exists — don't build a plan for the wrong race). Pull: distance, expected
  duration (from his goal time), elevation profile, aid-station locations,
  and the conditions section (historical temps, what finishers report about
  race-day weather).
- If altitude at the race venue is above ~1500m and the dossier doesn't
  cover it, note that explicitly — most races in Josh's history so far
  won't need this, but don't skip the check.

### 2. Ask Josh what he knows
One tight round of questions, not an interrogation:
- Gut carb tolerance — has he practiced fueling on long runs? At what
  rate, with what products, and how did his stomach handle it?
- Salty/heavy sweater? (visible salt stains, stinging eyes, salt taste,
  cramping history)
- Measured sweat rate, if he has one (pre/post weigh-in from a training run).
- What products he actually plans to use (gels, drink mix, chews, real food)
  — the plan should fit what he'll actually carry and tolerate, not a
  generic ideal.
- Heat tolerance — does he run/perform worse than expected in warm
  conditions?
- Any past fueling disasters (GI distress, bonking, cramping) worth
  designing around.

### 3. Estimate what he doesn't know
For anything unanswered, estimate from body weight and race conditions using
the typical ranges in the science section above. Rules:
- **Label every estimate clearly** (e.g. "ESTIMATED — no measured sweat
  rate") — never let an estimate look like a measured input in the final
  plan.
- **Give a one-line way to measure the real number later** next to each
  estimate (e.g. "measure by weighing yourself, in kit, immediately before
  and after a run of at least 60 min, no bathroom break mid-run; each kg
  lost ≈ 1L sweat, corrected for anything drunk").
- **Never stall.** If Josh doesn't know his sweat rate, estimate it — don't
  wait for him to go test it before building the plan.

Default estimate starting points (adjust for conditions/body size, and say
so):
- **Sweat rate:** ~0.5-0.8 L/hr for a cool-conditions steady effort at
  Josh's size, scaling up toward 1.0-1.5 L/hr as temperature/intensity rise.
  Bigger/heavier runners and hotter conditions sit at the top of the range.
- **Sweat sodium:** ~800-1000 mg/L as a population-average default; shift to
  1200-1600 mg/L if Josh reports any salty-sweater signs, or down toward
  500-700 mg/L if he reports none and sweat doesn't sting his eyes.
- **Gut carb tolerance:** if untested, assume the untrained default of
  ~45-60 g/hr (single-source-safe), not the 90 g/hr multiple-transportable-
  carb ceiling — that has to be earned through gut training, not assumed.

### 4. Build the fueling plan
- **Carbs/hr:** start from the duration bracket (30-60 g/hr for 1-2.5hr,
  up to 90 g/hr beyond that), then cap it at whichever is lower: the
  duration-bracket target, or Josh's actual/estimated gut tolerance. Show
  the math and say plainly if the target requires a glucose:fructose blend
  to hit (needed above ~60 g/hr).
- **Fluid/hr:** target ~ (sweat rate × 0.6-0.8) to keep body-mass loss under
  2%, capped at the ~1.0-1.2 L/hr absorption ceiling — if his estimated
  sweat rate exceeds that, say so explicitly rather than prescribing an
  undrinkable volume.
- **Sodium/hr:** sweat rate (L/hr) × sweat sodium concentration (mg/L) ×
  the fraction being replaced (roughly 50-100%, higher if salty-sweater
  signs or hot conditions, lower for shorter/cooler races where under-
  replacing is low-risk).
- **Timing:** map carbs/fluid/sodium onto the actual course — use the
  dossier's aid-station mile markers if available, otherwise a fixed
  interval (e.g. every 20 min) starting after ~15-20 min (not immediately
  at the gun). State exactly what to take and when, in plain terms Josh can
  follow without doing math mid-race.

### 5. Build the pacing plan
- Start from goal time ÷ distance for a flat target pace.
- Apply the Minetti grade-adjusted-pace ratio to the course's actual
  elevation profile (per segment or per mile, using whatever granularity
  the dossier's elevation data supports) so uphill miles get a slower
  target and downhill miles a faster one, holding effort roughly even
  rather than pace literally even.
- Apply a heat adjustment if conditions warrant, scaled to race duration
  (don't apply a full-marathon-sized adjustment to a shorter race).
- Apply an altitude adjustment only if the venue is meaningfully above
  ~1500m; otherwise state explicitly that altitude isn't a factor for this
  race.
- If the dossier already flags a course-specific pacing risk (e.g. a known
  late-race fade, crowd/pacer surge risk), fold that into the plan directly
  — e.g. a deliberately conservative opening-mile range — rather than
  repeating it as a separate warning.

### 6. Show the work, flag the limits, stay correctable
- Present a clear table of every input: **Josh's / Estimated**, the value,
  and (for estimates) the one-line "how to measure this for real."
- Show the formula and math behind each derived number (carbs/hr,
  fluid/hr, sodium/hr, pace per segment) — not just the final numbers.
- **Flag anything sitting at or near a physiological limit**: carb intake
  near/above 60 g/hr without a confirmed glucose:fructose product, fluid
  target above the ~1.2 L/hr absorption ceiling, sodium at the high end of
  the range, gut tolerance being asked to handle more than Josh has
  actually practiced.
- If Josh corrects an input (real sweat rate, different product, corrected
  body weight), **recompute the affected numbers and say what changed** —
  don't just patch the one line he corrected while leaving derived numbers
  stale.

## Save it

Write to `fueling-pace/<YYYY-MM-DD>-<race-name-slug>-plan.md`, dated to the
day the plan is built. Don't overwrite a past plan for the same race if one
already exists — a re-run means an input changed (real sweat-rate test back,
goal time revised, gut training progressed), and the history of how the plan
tightened up over the training block is worth keeping, same as `races/` and
`reviews/`. Note clearly at the top of the file which numbers are Josh's own
and which are estimates, so it's obvious at a glance what to dial in before
race day.

## Close the loop

Don't just save and dump the file — walk Josh through the fueling and
pacing plan conversationally, point out anything flagged at a limit, and
name the estimates that would most improve the plan if he measured them for
real before race day (usually sweat rate first, since it drives both fluid
and sodium targets).
