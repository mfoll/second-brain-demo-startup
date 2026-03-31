---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Exponential_backoff
date_accessed: 2026-03-20
licence: CC BY-SA 4.0
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[reminder-pipeline-overview]]"
  - "[[wikipedia-rate-limiting]]"
_organized: true
---

# Exponential backoff

## Summary

Wikipedia article on exponential backoff: an algorithm that uses feedback to multiplicatively decrease the rate of a process until it finds an acceptable rate, used widely in computer and wireless networks.

## Why It Matters

Postmortem action 5 ([[hamish-pettigrew]]): reminder workers now honor Pingrove's `Retry-After` when present and otherwise back off exponentially from 1 second up to 60 seconds with jitter, inside a 45 per second token bucket. See [[reminder-pipeline-overview]].

## Caveats

The article does not cover jitter in depth or API client libraries. Last edited 2026-10-05 at re-check.

## Source Links

- [Exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff), Wikipedia, CC BY-SA 4.0.
