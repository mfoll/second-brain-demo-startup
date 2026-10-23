---
type: Source
source_type: Internal memo
date_accessed: 2026-10-12
belongs_to: "[[platform-engineer-hire]]"
related_to:
  - "[[kwabena-asare]]"
  - "[[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]"
_organized: true
---

# Kwabena Platform Hire Memo

Three-page memo by [[kwabena-asare]], sent 2026-10-12, arguing that the first 2027 hire should be a platform engineer.

## Summary

The recurring pages come from three sources (reminder queue age, database connections, Pingrove errors) that each need weeks of sustained work, which the rotation never leaves time for. A platform engineer would own alerting, Terraform and the database, take primary during working hours, and let product engineers move to secondary-only.

## Key Details

- Uses the [[paging-report-2026-q3]] numbers and the Q2 trend.
- Lists the work he believes is stuck: PgBouncer pool tuning per tenant class, partitioning the reminder queue, resuming the [[observability-overhaul]], automated restore tests.
- Names the infrastructure bus factor: two people (himself and Bram).
- Estimates 6 to 8 fewer pages a week within two quarters of the hire. He marks this as a guess.

## Why It Matters

One of the two positions in [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]. Recorded as his position; my evaluation lives in the Question.

## Source Location

Engineering shared drive, `Planning / 2027 / hiring-case-platform`.
