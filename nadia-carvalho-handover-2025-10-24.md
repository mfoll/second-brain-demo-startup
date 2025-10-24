---
type: Event
date: 2025-10-24
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[nadia-carvalho]]"
  - "[[original-data-model-notes]]"
  - "[[teodora-vasilescu]]"
_organized: true
---

# Nadia Carvalho Handover 2025-10-24

Handover session before [[nadia-carvalho]] left on 2025-10-31. Two sessions of two hours with [[teodora-vasilescu]], [[hamish-pettigrew]] and me.

## What Was Handed Over

- Data model and migrations to Teodora, using [[original-data-model-notes]] as the spine.
- The reminder scheduler (the cron-like job that enqueues each day's reminders) to Hamish.
- Nadia's list of known weak spots: no database-level tenant enforcement, `reminder_deliveries` growing without partitions, and the scheduler assuming a single queue consumer.

## What We Did With It

- All three weak spots came back in 2026: tenant enforcement became the isolation debate ([[architecture-review-2025-11-18]]), `reminder_deliveries` was partitioned in 2026-02, and the single-consumer assumption made the March backlog worse.
- I should have turned her list into tickets that week. I turned it into a document.
