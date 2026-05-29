---
type: Source
source_type: Test report
date_accessed: 2026-05-29
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[migration-fan-out]]"
  - "[[teodora-vasilescu]]"
_organized: true
---

# Migration Load Test Results 2026-05

Results of postmortem action 9, run by [[teodora-vasilescu]] in staging between 2026-05-20 and 2026-05-28.

## Key Details

- Setup: 100 tenant databases on two staging instances behind PgBouncer, synthetic morning load including the reminder batch.
- With the throttle (4 databases, 8 connections each), a typical migration took 5 h 30 min across 100 databases; connections stayed under 40% of the limit; reminder queue age never exceeded 2 minutes.
- Without the throttle the staging primary hit its connection limit within 6 minutes, reproducing March.
- Conclusion in the report: safe but slow. Theo Mallory's review had already pointed to the bigger question of N itself.

## Source Location

Engineering shared drive, `Postmortems/2026-03-17-reminders/action-9-load-test`.
