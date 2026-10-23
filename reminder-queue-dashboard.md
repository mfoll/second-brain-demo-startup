---
type: Source
source_type: Dashboard
date_accessed: 2026-10-20
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reminder-pipeline-overview]]"
  - "[[what-is-our-reminder-delivery-target]]"
_organized: true
---

# Reminder Queue Dashboard

The dashboard for the reminder pipeline, built after the March outage.

## Key Details

- Panels: queue depth and oldest job age, sends per second against the 45 per second cap, Pingrove 429 and 5xx rates, delivery receipts within 10 minutes, expired reminders per day.
- Weekday morning batch: about 38,000 reminders queued between 06:00 and 06:15, drained by about 06:35.
- Share sent within 15 minutes of schedule, 2026-Q3: 99.82%.

## Source Location

Metrics dashboard "Reminders", linked from [[alerting-rules-inventory]] and the [[on-call-handbook]].
