---
type: Project
status: Completed
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[kwabena-asare]]"
  - "[[on-call-rotation-redesign]]"
has:
  - "[[reminder-outage-2026-03-17]]"
  - "[[postmortem-review-2026-03-24]]"
  - "[[reminder-outage-postmortem-document]]"
  - "[[run-an-incident]]"
_organized: true
---

# Reminder Outage Postmortem

The postmortem of the 2026-03-17 reminder outage and the follow-through on its action items.

## Outcome

Postmortem of the 2026-03-17 outage published and all 9 action items closed. Reached on 2026-05-29.

## Current State

- Completed. The published document is [[reminder-outage-postmortem-document]]; the review meeting is [[postmortem-review-2026-03-24]].
- All 9 actions closed; the last one (a load test of migration fan-out at 100 databases) closed on 2026-05-29.
- No connection-exhaustion incident since PgBouncer went live on 2026-04-14.

## Scope and Boundaries

The incident on 2026-03-17 from 09:40 to 18:55: 4,212 appointment reminders for 61 clinics delayed or never sent. In scope: timeline, causes, customer communication and the 9 actions. Out of scope: the decision to reverse the tenant isolation model, which drew on this incident but was made separately at [[architecture-review-2026-06-11]].

## Working Context

- Causes in one line: a tenant-migration batch opened one connection per tenant database and exhausted the RDS connection limit; the reminder workers starved, and their retries then hit the Pingrove rate limit. Details in [[reminder-outage-2026-03-17]].
- Of the 4,212 reminders, 2,947 went out late and 1,265 were never sent because the appointment had already passed.
- [[kwabena-asare]] was incident commander; [[pablo-arriaga]] handled clinic communications; I was the scribe for the first two hours, which was a mistake I wrote up in [[incident-commander-should-not-be-the-founder]].
- [[hana-kovarik]]'s imaging center was the account hit hardest (412 reminders).

The 9 actions and their owners:

1. PgBouncer in transaction mode in front of the primary ([[kwabena-asare]], closed 2026-04-14).
2. Throttle on migration jobs: at most 4 databases in parallel and 8 connections each ([[teodora-vasilescu]], closed 2026-04-03).
3. Alert on reminder queue age over 10 minutes (Kwabena, closed 2026-03-27).
4. On-call redesign, handed to [[on-call-rotation-redesign]] (closed 2026-05-15).
5. Reminder workers honor Pingrove's `Retry-After` and send through a 45 per second token bucket ([[hamish-pettigrew]], closed 2026-04-10).
6. A reserved connection budget for the reminder workers' database role (Kwabena, closed 2026-04-08).
7. Clinic communication templates and a status page ([[pablo-arriaga]] and [[imani-brooks]], closed 2026-04-20).
8. An "unsent reminders" report so clinics can phone patients themselves ([[lucia-ferreyra]], closed 2026-05-06).
9. Load test of migration fan-out at 100 databases (Teodora, closed 2026-05-29).

## Next Actions

None. Closed.

## Important Notes

- [[reminder-outage-2026-03-17]]
- [[postmortem-review-2026-03-24]]
- [[connection-exhaustion]]
- [[pingrove-retry-correspondence]]

## Maintenance Log

- 2026-05-29: Last action closed; project completed.
- 2026-04-14: PgBouncer live.
- 2026-03-27: Postmortem document published to the whole company.
- 2026-03-24: Blameless review held.
- 2026-03-17: Incident.
