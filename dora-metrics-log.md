---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-10-05
belongs_to: "[[engineering-metrics]]"
related_to:
  - "[[dora-four-keys]]"
  - "[[which-engineering-metrics-should-we-show-the-board]]"
_organized: true
---

# DORA Metrics Log

My monthly sheet of the four DORA measures since 2026-05, filled by hand from GitHub Actions deploy runs and the incident list. See [[dora-four-keys]] for definitions and the Q3 values.

## Key Details

- One row per month: deploys, median lead time, changes that needed a rollback or hotfix within 24 hours, incidents and median restore time.
- May and June show the outage clean-up: deploy frequency up, change failure rate at 9%.
- July to September: about 11 deploys a week, change failure rate about 6%.

## Caveats

Hand-filled, by one person, 20 minutes a month. Good enough for direction, not for a board slide without a caveat.

## Source Location

My folder in the leadership shared drive, `Metrics / dora-log`.
