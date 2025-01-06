---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[pingrove-api-documentation]]"
  - "[[hamish-pettigrew]]"
_organized: true
---

# Reminder Pipeline Overview

How an appointment reminder gets from the database to a phone. The part of the system clinics notice first when it fails.

## Flow

1. **Scheduler** (`quaylane-workers/scheduler`, owner [[hamish-pettigrew]]): every 5 minutes, and in a big batch at 06:00, finds appointments due a reminder per each clinic's rules (for example 24 hours and 2 hours before) and enqueues one job per reminder.
2. **Queue**: Redis-backed, `reminders` queue, separate from imports and exports so they cannot block it.
3. **Reminder workers**: 8 tasks. Each job renders the clinic's template, checks the appointment still exists, and sends.
4. **Sending**: SMS through Pingrove, paced by a token bucket at 45 per second across all workers, honoring `Retry-After` and backing off exponentially otherwise, with an idempotency key. Email through a separate provider, no shared limit.
5. **Receipts**: Pingrove webhooks update `reminder_deliveries`.
6. **Expiry**: a job whose appointment time has passed is dropped and counted in the unsent reminders report.

## Volumes

About 38,000 SMS on a weekday, 800,000 reminders a month across channels. The 06:00 batch drains in about 35 minutes.

## Guardrails Since March

Reserved database pool for the `ql_reminders` role, queue-age alert at 10 minutes, Pingrove's 429 notice. See [[reminder-outage-postmortem]] and [[reminder-queue-dashboard]].
