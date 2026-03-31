---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Rate_limiting
date_accessed: 2026-03-20
licence: CC BY-SA 4.0
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[pingrove-call-2026-03-19]]"
  - "[[noisy-neighbor]]"
_organized: true
---

# Rate limiting

## Summary

Short Wikipedia article on rate limiting: controlling the rate of requests sent or received by a network interface, used for example against denial-of-service attacks and web scraping.

## Why It Matters

Background for the [[pingrove-call-2026-03-19]]. Pingrove's 50 messages per second is a rate limit on the receiving side; our 45 per second token bucket is one on the sending side. Per-tenant API limits for [[noisy-neighbor]] cases would be a third kind.

## Caveats

Thin article; network-oriented. Last edited 2026-09-02 at re-check.

## Source Links

- [Rate limiting](https://en.wikipedia.org/wiki/Rate_limiting), Wikipedia, CC BY-SA 4.0.
