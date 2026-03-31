---
type: Event
date: 2026-03-19
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[bettina-solberg]]"
  - "[[pingrove-retry-correspondence]]"
  - "[[wikipedia-rate-limiting]]"
_organized: true
---

# Pingrove Call 2026-03-19

Call with [[bettina-solberg]] and a Pingrove support engineer two days after the [[reminder-outage-2026-03-17]]. Kwabena, Hamish and me.

## What We Learned

- The limit is 50 messages per second per account, enforced on a one-second window. Above it Pingrove returns HTTP 429 with `Retry-After` in seconds.
- On 2026-03-17 between 11:10 and 14:15 our account sent about 1.9 million requests, of which about 1.86 million were rejected. Our workers retried each rejection immediately.
- Pingrove does not raise limits for burst recovery. They offered a second sender account at a monthly fee.

## Agreed

- We honor `Retry-After` and pace sends with a token bucket at 45 per second (postmortem action 5, [[hamish-pettigrew]]).
- Pingrove will notify our on-call email if 429s exceed 10% of our requests over 5 minutes. Live since 2026-04-02.
- Second sender account: declined for now, revisit with [[should-reminders-fall-back-to-email-when-sms-is-throttled]].

## Follow-up

The written summary they sent is in [[pingrove-retry-correspondence]].
