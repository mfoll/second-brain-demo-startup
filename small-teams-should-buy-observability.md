---
type: Opinion
status: Active
confidence: Medium
belongs_to: "[[observability-overhaul]]"
related_to:
  - "[[wikipedia-observability-software]]"
  - "[[platform-engineering]]"
_organized: true
---

# Small Teams Should Buy Observability

## Stance

A team of eight engineers should pay for a hosted tracing and metrics backend and spend its own time only on instrumentation and context propagation, never on running the backend.

## Why I Think This

- The hard part in our spike was propagation through the queue, which no vendor does for us; the backend was trivial to rent ([[tracing-spike-notes-2025-09]]).
- Research like [[xing-2025-microservice-anomaly-detection-fault-localization]] is about scale we will not have for years.
- Kwabena is the only person who could run a self-hosted stack, and he is already the bottleneck.

## What Would Change My Mind

Hosted pricing at full volume above roughly $2,000 a month, or a customer data-residency requirement that excludes the vendor.

## Implications

Price the paid tier for [[engineering-budget-2027]] before the 2027-Q1 restart.
