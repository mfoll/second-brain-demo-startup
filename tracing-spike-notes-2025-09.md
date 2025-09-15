---
type: Source
source_type: Internal document
date_accessed: 2025-09-15
belongs_to: "[[observability-overhaul]]"
related_to:
  - "[[kwabena-asare]]"
  - "[[opentelemetry-docs-javascript]]"
_organized: true
---

# Tracing Spike Notes 2025-09

[[kwabena-asare]]'s write-up of the two-week tracing spike that opened the [[observability-overhaul]], 2025-09-01 to 2025-09-12.

## Key Findings

- OpenTelemetry auto-instrumentation for HTTP, Express and `pg` worked in `quaylane-api` in a day.
- Queue jobs lose trace context: the Redis job payload needs the context injected on enqueue and extracted in the worker. About a week of work across `quaylane-api` and `quaylane-workers`.
- Head sampling at 10% keeps the hosted backend on its free tier at our volume.
- Half-instrumented paths produced traces that ended at the queue, which misled us twice during the spike.

## Source Location

Engineering shared drive, `Platform/observability/spike-2025-09`.
