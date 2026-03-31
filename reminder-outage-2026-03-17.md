---
type: Event
date: 2026-03-17
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[connection-exhaustion]]"
  - "[[kwabena-asare]]"
  - "[[pablo-arriaga]]"
  - "[[full-tenant-database-rollout]]"
_organized: true
---

# Reminder Outage 2026-03-17

From 09:40 to 18:55 on Tuesday 2026-03-17, 4,212 appointment reminders for 61 clinics were delayed or never sent. Our worst incident so far.

## At a Glance

> [!abstract]
> A tenant-migration batch opened one connection per tenant database and exhausted the RDS connection limit on the primary. The reminder workers could not reach the database and their jobs piled up; when connections came back, the retries hit Pingrove's rate limit of 50 messages per second and throughput collapsed. 2,947 reminders went out late and 1,265 were never sent. Kwabena Asare was incident commander, Pablo Arriaga handled clinic communications.

## Impact

- 61 clinics affected, 4,212 reminders. Of these, 2,947 sent late (median delay 3 h 10 min) and 1,265 never sent because the appointment had already passed.
- The admin web app was slow or erroring between 09:40 and 10:55 for all tenants (connection errors on about 30% of API requests).
- Hardest hit: [[hana-kovarik]]'s imaging center, 412 reminders.
- No data was lost or exposed.

## Timeline

- 09:31 Migration batch for QL-1432 (new columns on `appointments` for waitlist autofill) started across the shared database and 21 tenant databases on the primary, with 24 workers each holding connections to every database it touched.
- 09:40 Connections reached the instance limit of 3,276. API requests and reminder workers began failing with "too many clients".
- 09:52 First support ticket. 09:58 API error-rate alert paged [[kwabena-asare]].
- 10:05 Kwabena declared SEV1 and took incident command. [[pablo-arriaga]] took communications. I acted as scribe, which I should not have.
- 10:30 First clinic update; then every 30 minutes.
- 10:48 Migration batch stopped. Connections back to about 1,400 by 10:55.
- 11:05 Reminder workers resumed with a backlog of about 3,800 jobs, all retrying immediately with no backoff.
- 11:10 Pingrove began answering HTTP 429. The workers retried each 429 at once, so most of our sending capacity went into rejected requests. Effective throughput fell to about 8 messages a second.
- 11:10 to 12:40 We investigated Pingrove as the cause because that is where the errors showed. [[bettina-solberg]]'s team confirmed the limit at 12:25.
- 12:40 [[hamish-pettigrew]] found that workers ignored `Retry-After`.
- 14:15 Hotfix: reminder worker concurrency capped to stay under 45 messages a second, reviewed by Teodora and deployed.
- 14:30 Worker job filter changed to drop reminders whose appointment had passed, so the backlog stopped growing with useless work.
- 18:55 Backlog cleared, queue age under 2 minutes. Incident closed.

## Causes

1. [[migration-fan-out]] on a single instance: the batch multiplied connections by the number of tenant databases. See [[connection-exhaustion]].
2. No reserved connections for the reminder workers.
3. No backoff and no respect for `Retry-After` in the Pingrove client, a textbook [[wikipedia-thundering-herd-problem]].
4. No alert on reminder queue age; we learned from a support ticket.

## Follow-up

- Blameless review on 2026-03-24: [[postmortem-review-2026-03-24]], 9 actions.
- Postmortem project: [[reminder-outage-postmortem]]. Published document: [[reminder-outage-postmortem-document]].
- Pingrove call on 2026-03-19: [[pingrove-call-2026-03-19]].
- The rollout paused until 2026-04-09: [[full-tenant-database-rollout]].
