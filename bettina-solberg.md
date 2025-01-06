---
type: Person
related_to:
  - "[[pingrove-retry-correspondence]]"
  - "[[pingrove-call-2026-03-19]]"
  - "[[reminder-pipeline-overview]]"
_organized: true
---

# Bettina Solberg

Account manager at Pingrove, the SMS gateway that sends Quaylane's appointment reminders.

## Context

Our account sends about 38,000 SMS a day on weekdays. Pingrove's rate limit is 50 messages per second per account; above that it answers HTTP 429 with a `Retry-After` header.

## How We Work Together

- Quarterly account review with [[kwabena-asare]] and me; ad hoc email when something goes wrong.
- After the [[reminder-outage-2026-03-17]] she arranged a call on 2026-03-19 ([[pingrove-call-2026-03-19]]) with one of their engineers. She was clear that the limit would not be raised for a retry storm, and equally clear that our workers had been ignoring `Retry-After`. Both points were fair.
- She offered a second sender account for burst capacity at extra cost. We declined for now; it is noted in [[should-reminders-fall-back-to-email-when-sms-is-throttled]].

## Current Threads

- Contract renewal in 2027-02; pricing per message is part of [[engineering-budget-2027]].
- Pingrove's vendor security documentation is an input to the vendor risk rows of the [[soc2-control-matrix]].

## Links

[[pingrove-retry-correspondence]], [[reminder-outage-postmortem]].
