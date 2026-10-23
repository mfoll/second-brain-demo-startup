---
type: Source
source_type: Internal dashboard
date_accessed: 2026-10-19
belongs_to: "[[partner-with-customers]]"
related_to:
  - "[[imani-brooks]]"
  - "[[customer-feedback-loop]]"
_organized: true
---

# Support Ticket Dashboard

Customer success's dashboard over the help desk: ticket volume, first response time, categories and engineering escalations.

## Summary

- About 520 tickets a month in 2026, roughly 0.27 per admin user.
- First response median 38 minutes in business hours.
- Escalations to engineering: 31 a month on average, 12 in a quiet month, 96 in 2026-03.

## Why It Matters

I read it every Wednesday before the escalation review with Imani. It is how I see whether a release created confusion: 3.0 GA day had 38 tickets against 22 on a normal Tuesday ([[version-3-general-availability-2026-09-15]]).

## Key Details

- Categories: how-to 46%, configuration 21%, reminders 14%, bugs 9%, billing 10%.
- Engineering escalations need a `QL-` ticket within one business day.

## Caveats

Category is set by the agent at closing and drifts; "configuration" and "how-to" overlap.

## Source Location

Help desk reporting view "Support overview", owned by Imani. Engineering leads have read access.
