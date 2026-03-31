---
type: Source
source_type: Vendor documentation
date_accessed: 2026-03-20
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reminder-pipeline-overview]]"
  - "[[bettina-solberg]]"
_organized: true
---

# Pingrove API Documentation

Pingrove's developer documentation for the SMS send API, as available to account holders.

## Key Details

- Send endpoint accepts one message per request; batch endpoint up to 100.
- Rate limit 50 messages per second per account; HTTP 429 with `Retry-After` above it.
- Delivery receipts by webhook, usually within 30 seconds; we store them in `reminder_deliveries`.
- Idempotency key header supported; we started sending it in 2026-04 so retries cannot double-send.

## Why It Matters

We had read the rate limit and not the `Retry-After` section. Both are on the same page.

## Source Location

Pingrove developer portal, logged in with the engineering vendor account. PDF snapshot of the relevant pages in `Vendors/Pingrove` on the engineering drive, taken 2026-03-20.
