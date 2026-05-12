# Status Report

**Source:** `.claude/examples/html-effectiveness/11-status-report.html`

## When

Weekly / bi-weekly engineering status. "What shipped, what slipped, what's next, one chart." Skimmable on Monday morning.

## Anatomy

- Page header — team name, week N, dateline
- `<section>` Highlights — 2-4 callout cards (what mattered most)
- `<section>` Shipped — list of completed items, often with PR / link badges
- `<section>` Velocity — small inline SVG bar chart, "metric we watch"
- `<section>` Carryover — items moved to next week with reason
- `<section>` Risks / blockers (optional)
- `<section>` On deck — what's planned

## Sections to Replace

1. `<title>` + h1: `<Team> — Engineering Status — Week N`
2. Eyebrow: dates (e.g. `Mar 4 – Mar 10`)
3. Highlights: short noun phrases, one sentence each
4. Shipped: list items, each with item name + 1-line value statement
5. Velocity chart: replace SVG `<rect>` heights and labels with actual numbers
6. Carryover / on-deck: bulleted list

## Customization Knobs

- Replace bar chart with line, stacked bar, or sparkline (keep `--clay` for primary, `--olive` for secondary, `--oat` for muted).
- Add a "decisions made" section for steering committees.
- Adjust card count per row via the existing grid.

## Pitfalls

- Don't dump JIRA exports — curate. The format earns trust by being short.
- Numbers without comparison are noise — every metric should have a delta vs prior period.
- Don't link out to internal-only URLs without flagging audience.
- Velocity chart: if data is flat, just say so in prose; don't ship a misleading chart.
