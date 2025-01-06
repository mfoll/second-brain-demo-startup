---
type: Topic
related_to:
  - "[[run-the-platform]]"
  - "[[team-health]]"
  - "[[kwabena-asare]]"
_organized: true
---

# Reliability And Incidents

Everything about keeping Quaylane up and what we do when it is not: incidents, postmortems, alerting, capacity and the reminder pipeline that clinics notice first when something breaks.

## Where We Are

The defining incident is the [[reminder-outage-2026-03-17]]: 4,212 reminders for 61 clinics delayed or never sent. Its [[postmortem-review-2026-03-24]] produced 9 actions, all closed by 2026-05-29, and changed who runs incidents (Kwabena, not me). Since 2026-04 we have had two SEV2 incidents and no SEV1, recorded in the [[incident-log]].

## Key Notes

- How we respond: [[run-an-incident]], [[on-call-handbook]], [[ship-an-emergency-change]].
- What we learned: [[reminder-outage-postmortem]], [[reminder-outage-postmortem-document]], [[incident-commander-should-not-be-the-founder]].
- Mechanics: [[reminder-pipeline-overview]], [[connection-exhaustion]], [[transaction-pooling]], [[error-budget]].
- Open: [[what-is-our-reminder-delivery-target]], [[should-reminders-fall-back-to-email-when-sms-is-throttled]], [[when-do-we-resume-the-observability-overhaul]].

## Reading

- [[wikipedia-site-reliability-engineering]], [[wikipedia-service-level-objective]], [[wikipedia-postmortem-documentation]].
- [[wikipedia-thundering-herd-problem]] and [[wikipedia-exponential-backoff]] describe exactly what our retries did to Pingrove.
- [[reliability-reading-list]] collects the rest.

## Related Topics

[[multi-tenancy]] (the outage came from a tenant migration), [[team-health]] (on-call load), [[platform-engineering]] (who should own this work).
