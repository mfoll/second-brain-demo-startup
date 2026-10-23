---
type: Source
source_type: Internal report
date_accessed: 2026-10-05
belongs_to: "[[on-call-rotation-redesign]]"
related_to:
  - "[[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]"
  - "[[how-many-pages-a-week-is-too-many]]"
  - "[[alert-fatigue]]"
_organized: true
---

# Paging Report 2026-Q3

Quarterly paging review for 2026-07-01 to 2026-09-30, compiled by [[kwabena-asare]] from the PagerDuty export and the Monday handoff notes.

## Summary

117 pages in 13 weeks, about 9 a week, down from about 13 a week in Q2. 38 pages out of hours (after 19:00 or at weekends), about 3 a week. The secondary was paged 9 times.

## Key Details

| Alert | Pages | Out of hours |
| --- | --- | --- |
| Reminder queue age over 10 minutes | 31 | 12 |
| Database connections over 85% | 19 | 7 |
| Pingrove delivery errors (via queue age or 5xx) | 17 | 6 |
| API 5xx over 2% | 28 | 8 |
| Login failures, including SSO | 22 | 5 |

- Median time to acknowledge: 4 minutes. Median time to resolve: 22 minutes.
- Two incidents of severity 2; no severity 1.
- Five alert rules demoted to `#alerts` during the quarter.

## Why It Matters

The main evidence for [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]. Kwabena reads the three recurring sources as platform work nobody has time for; Felix reads the downward trend as evidence that the problem is already shrinking. Both readings fit the data.

## Caveats

Pingrove errors surface through two different alerts, so the row is an estimate from the handoff notes. Page counts do not capture severity.

## Source Location

PagerDuty analytics export and the `On-call / Quarterly reviews` folder in the engineering shared drive.
