---
name: regenerate-dashboard
description: Regenerate dashboard.html — the one-page snapshot of Josh's training (race countdown, today's readiness, this week's sessions, volume/pace trends, PRs, and coaching notes), rebuilt from real Garmin data plus the current training/reviews/health files. Use when Josh asks to "regenerate the dashboard", "update the dashboard", "refresh the dashboard", or runs /regenerate-dashboard — including as the last step after a /weekly-review + /plan-my-week pass.
---

# /regenerate-dashboard — rebuild the one-page snapshot

`dashboard.html` is a static, self-contained snapshot — not a live app. It
gets fully rewritten each time this runs, from whatever's true right now in
Garmin + the project files. There's only ever one copy (no dated versions);
regenerating replaces it. It should always open standalone in a browser,
with no external requests (fonts, scripts, images) — everything inline.

## When to run this

- Josh asks directly ("regenerate the dashboard", "refresh it").
- As the natural last step after `/weekly-review` + `/plan-my-week` — the
  dashboard's "this week" and "readiness" sections go stale the moment a
  new week is planned, so offer to regenerate it then rather than leaving
  it showing last week.

Don't run it speculatively mid-conversation for unrelated changes (e.g. a
one-off Garmin question) — only when the underlying data has actually moved.

## 1. Read the current dashboard first

Read the existing `dashboard.html` before touching anything. The `<style>`
block (the whole design system — colors, card layout, chart CSS, dark/light
mode via `prefers-color-scheme`) should be preserved as-is unless Josh has
asked for a visual change. This skill replaces the *content* inside `<body>`,
not the design.

## 2. Gather what's changed

**From the project files:**
- `athlete-profile.md` — goal race, date, target time, zones (for the hero
  and readiness sections).
- `training/plan.md` — current phase, phase dates, total build length (for
  the "% through the build" progress bar).
- The most recent `training/<Monday>-week.md` — this week's actual planned
  sessions, in order, with targets.
- The most recent 1-2 files in `reviews/` — for the coaching-overview
  paragraph and insight list; don't re-derive analysis from scratch, reuse
  the judgment already reached there.
- Any recent file in `health/` — if a readiness flag was written in the
  last day or two, that's more specific than a fresh Garmin pull alone.
- `races/*-dossier.md` if present — course facts for context if relevant.

**From Garmin (`garmin_mcp`), read-only, live — do not cache into files
beyond what's already in dashboard.html:**
- Today's readiness: `get_morning_training_readiness` or
  `get_training_readiness` for today's date — score, and the specific
  factors driving it (HRV, sleep, acute load) so the "why" text is
  evidence-based, not generic.
- This week's completed activities so far: `get_activities_by_date` for
  the current week-to-date, to mark sessions "Done" vs "Upcoming" in the
  sessions list, matching against the dated week-file's plan.
- Weekly volume trend: aggregate running distance per calendar week for
  roughly the last 7 weeks (`get_activities_by_date` per week, or
  `get_weekly_intensity_minutes`/`get_training_load_trend` if that's
  faster) — mirrors the existing bar chart.
- Recent paces: the last ~9 runs (`get_activities`), avg pace and HR per
  run, for the pace line chart.
- PRs: `get_personal_record` for 5K/10K/half-marathon if available;
  otherwise use the best documented time from `athlete-profile.md` or past
  reviews and note the source.

**From the filesystem:**
- List `.claude/skills/` and use the actual set of skill folders (name +
  the one-line `description` from each `SKILL.md` frontmatter, shortened
  to a phrase) for the skills grid — don't hand-maintain a hardcoded list
  that can drift from what actually exists.

## 3. Rebuild each section

- **Header**: "Snapshot: <today's full date>".
- **Hero**: days-to-race (today → race date), target time, % through the
  build (days elapsed in the current build / total build length from
  `plan.md`'s phase table).
- **Readiness card**: today's score, level, and a 2-3 sentence evidence-based
  "why" — same evidentiary bar as `/recovery-check`: name the specific
  numbers driving it, not a vibe.
- **This week's sessions**: pull straight from the current dated week-file,
  in day order, tagging each `Done` / today's session `Go easy`/`Go hard`
  (matching the readiness call) / others `Upcoming`.
- **Weekly volume chart**: rescale the SVG bars to the actual 7-week data
  (recompute bar heights/positions the same way the existing chart does —
  keep the same viewBox and scale logic, just feed it real numbers).
- **Recent paces chart**: same approach for the pace line chart — plot
  actual pace-per-run, annotate the fastest/slowest same as before.
- **PR tiles**: update times/dates/notes only if something changed.
- **Coaching section**: overview paragraph and 3-4 insights, each still
  tagged to the coaching-philosophy influences already established in
  `athlete-profile.md` (van den Broek, Bakken, Roche, Skevington) where a
  real parallel exists this week — don't force a tag that doesn't fit.
  Pull the substance from the latest `reviews/` entry rather than
  re-analyzing from raw data.
- **Tips**: 3-4 concrete, this-week-specific action items — not generic
  advice.
- **Skills grid**: regenerate from the actual `.claude/skills/` listing
  (see step 2).
- **Footer**: "Snapshot generated <today's date> from Garmin +
  training/ + reviews/ + races/ + health/ — regenerate to refresh."

## 4. Keep it honest

Same "accountability, not flattery" bar as everything else in this project
— if the week is behind plan, the dashboard says so; if a chart would
misrepresent a partial/in-progress week (like the current week always is,
since it's not over), mark it clearly as in-progress rather than plotting
it as if it were a completed week's total.

## 5. Save and confirm

Overwrite `dashboard.html` in place (single file, no dated copies). Tell
Josh what changed since the last regeneration (new week plotted, readiness
score updated, any new PR) rather than just "done" — a one-line diff
summary, not a full re-walkthrough of the whole page.
