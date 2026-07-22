---
name: race-planner
description: Build Josh a deep race dossier for his goal race — the course (official info + real finisher reports, not just the race website), typical race-day conditions, what finishers warn about, gear/logistics, and an honest read of his own readiness against the course's specific demands, pulled from his real Garmin data and athlete-profile.md. Ends by asking what worries him and locking in A/B/C goals, then a "what this means I need to train" list. Saves a dated file to races/. Use when Josh asks to "plan for [race]", "research my race", "build a race dossier", or runs /race-planner.
---

# /race-planner — build a race dossier

This is not a copy of the race's own marketing page. It exists to answer
one question honestly: **given this specific course and Josh's specific
fitness right now, what is he ready for and where is he exposed?** Every
dossier this produces should be defensible — grounded in cited sources,
grounded in Josh's real data, and explicit about what's uncertain.

## Which race

Default to the goal race in `athlete-profile.md` (currently the Ealing
Half Marathon, 2026-09-27). If Josh names a different race, or if
`athlete-profile.md` has no goal race set, ask him directly rather than
guessing — don't build a dossier for the wrong event.

## Research — go deep, cite everything

Don't stop at the official race website. For each area below, search
broadly and fetch real pages (not just search-result snippets) before
writing anything. Every factual claim in the dossier needs a source link
next to it. If two sources disagree (e.g. elevation-gain figures, start
vs. finish location across route-change years), report both and say so —
don't silently pick one. If something is genuinely uncertain or you
couldn't verify it, say that plainly rather than smoothing it over.

**1. The course.** Distance, elevation profile (total gain, where the
climbs/descents actually are, steepest sections), surface, technical
sections, altitude if relevant. Pull the official course/route page(s)
AND at least 3-4 independent finisher race reports/blogs/forum threads —
official pages describe the route, finishers describe what it's actually
like to run. Note if the course has changed years (a route change means
older reports may describe a different race).

**2. The conditions.** Actual historical weather for that date/location
— not just "average September weather" but the specific week, pulled
from a real historical-weather source (WeatherSpark, Met Office, etc.),
plus what finishers say the conditions are actually like on the ground
(sun exposure, wind corridors, humidity in the crowd, etc.).

**3. What finishers warn about.** The parts people underestimate, common
mistakes, where the race tends to fall apart (a specific mile, a fueling
mistake, going out too hot behind pacers). Weight reports from finishers
at a similar level/experience to Josh over elite race recaps — a sub-3
marathoner's "warning" isn't calibrated to an 8-week-back athlete's race.

**4. Gear and logistics.** Gear suited to the actual conditions and
terrain (not generic packing lists). Travel, parking/transport, packet
pickup timing and location, bag drop, start corrals/waves, start time.

## Make it about Josh

This is the section that makes it a dossier and not a Wikipedia article.

### 1. Read his standing context
- `athlete-profile.md` in full — goals, zones, injury history, the
  Coaching Philosophy section, `training/plan.md`'s "Limiters, ranked"
  if present.
- The most recent 1-2 files in `training/` and `reviews/` for how
  training has actually been going lately, not just the plan's intent.

### 2. Pull real current fitness from Garmin
At minimum: recent activities (distance, pace, HR — checking the Z2/Z3
aerobic-efficiency gap if that's a known limiter), training
readiness/HRV, training status/load (ACWR, aerobic balance feedback),
VO2max trend, race predictions (report as an algorithmic ceiling, not a
target — same treatment as elsewhere in this project), and hill
score/elevation data on recent runs specifically (this race's terrain
demand only matters if Josh has trained for it — check directly whether
he has).

### 3. Match course demands to real readiness — specifically, not generically
For each demand the course actually has (distance vs. his long-run
ceiling, hills vs. his hill-score/elevation data, heat/technical terrain
vs. what he's trained in, etc.), say plainly whether he's ready or
exposed, and why, citing the actual numbers on both sides. The standard
here is "your long-run durability is there, but you have almost no steep
technical descending and this course is full of it" — specific gaps tied
to specific evidence, not a vague confidence rating. If Garmin access
fails or data's too thin to judge something, say so and ask Josh
directly rather than guessing at his fitness.

## Before finishing — ask, don't assume

Ask Josh directly:
1. **What worries him most about this race** — don't guess this, it
   changes what the dossier should emphasize.
2. **His A / B / C goals** — lock these in explicitly if not already
   set for this race in `athlete-profile.md`.

Fold his answers into the dossier before considering it done.

## Close every dossier with

- **"What this means I need to train"** — a short list, each item tied
  to a specific gap found in the readiness section above (not generic
  training advice).
- **A / B / C goals**, each with a one-line rationale tying it to the
  course demands and his current fitness (e.g. why B is the honest
  target given the aerobic-efficiency gap, why A is the upside case if
  a specific limiter closes in time).

## Save it

Write to `races/<YYYY-MM-DD>-<race-name-slug>-dossier.md`, dated to
today (the day the dossier is built, not the race day). Never overwrite
an existing dossier for the same race — if Josh's readiness or goals
change materially before race day, that's a reason to re-run this skill
and save a new dated file, so the history of how the read on this race
evolved is preserved (same principle as `reviews/` never being
overwritten).
