---
type: Source
source_type: Internal benchmark report
date_accessed: 2026-07-24
belongs_to: "[[multi-location-calendars]]"
related_to:
  - "[[lucia-ferreyra]]"
  - "[[multi-location-calendars-design-doc]]"
_organized: true
---

# Calendar Performance Benchmark 2026-07

Lucia's benchmark of the cross-site calendar view before and after the July performance work.

## Summary

- 40-site week view at p95: 4.8 s in June, 1.4 s after the changes on 2026-07-24.
- Changes: windowed rendering of the grid, a narrower API payload (only the fields the grid draws), and one query per view instead of one per site.

## Why It Matters

Meridale's coordinators open a view of all their sites every morning. At 4.8 s the feature would have been unusable for them, which is part of why multi-location calendars could not ship in June. The benchmark closed that risk before wave 1.

## Key Details

| View | June p95 | July p95 |
| --- | --- | --- |
| 1 site, day | 0.6 s | 0.4 s |
| 10 sites, week | 2.1 s | 0.8 s |
| 40 sites, week | 4.8 s | 1.4 s |

Measured on staging with a copy of the pilot clinics' configuration scaled to 40 sites with synthetic appointments.

## Caveats

Synthetic data has evenly spread appointments; real books cluster in the morning. Production numbers after wave 2 are close: 1.6 s at p95.

## Source Location

`quaylane-web/benchmarks/2026-07-calendar.md` and the dashboard panel "Calendar p95 by site count".
