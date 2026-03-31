---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Thundering_herd_problem
date_accessed: 2026-03-20
licence: CC BY-SA 4.0
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[reminder-outage-2026-03-17]]"
  - "[[wikipedia-exponential-backoff]]"
_organized: true
---

# Thundering herd problem

## Summary

Wikipedia article on the thundering herd problem: many processes or threads are woken at once for an event or a newly available resource, only one can use it, and the rest fail and go back to sleep, wasting resources and slowing the one that succeeds.

## Why It Matters

[[hamish-pettigrew]] linked this in the incident channel at 12:45 on 2026-03-17. Our case was a close cousin rather than the textbook one: when connections came back, about 3,800 reminder jobs retried at once against a gateway that accepts 50 messages a second, and each rejection was retried immediately. The fix combined backoff ([[wikipedia-exponential-backoff]]) with pacing under the limit.

## Caveats

The article is about process wake-ups in operating systems and networking; applying it to API retries is our analogy. Last edited 2026-05-27 at re-check.

## Source Links

- [Thundering herd problem](https://en.wikipedia.org/wiki/Thundering_herd_problem), Wikipedia, CC BY-SA 4.0.
