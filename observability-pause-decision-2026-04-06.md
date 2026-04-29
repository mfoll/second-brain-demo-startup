---
type: Event
date: 2026-04-06
belongs_to: "[[observability-overhaul]]"
related_to:
  - "[[soc2-type-1-audit]]"
  - "[[kwabena-asare]]"
_organized: true
---

# Observability Pause Decision 2026-04-06

Decision in my one-to-one with [[kwabena-asare]] to pause the [[observability-overhaul]].

## Why

- Kwabena was the only person working on tracing and also the owner of most infrastructure controls for the [[soc2-type-1-audit]]: access reviews for AWS, backup evidence, change management in `quaylane-infra`.
- He also owned three open postmortem actions, including PgBouncer.
- The Type I report had to land before Meridale's 2026-09-30 deadline. Tracing had no deadline.

## What We Kept

API tracing stays on at 10% head sampling, with a CI smoke test. Nothing new is instrumented.

## What We Gave Up

Worker traces would have shortened the diagnosis of the March outage. We accepted that risk for six months. Resumption is planned for 2027-Q1, tracked in [[when-do-we-resume-the-observability-overhaul]].

## Note to Self

This was the right call and I still feel it as a loss. The pattern of pausing reliability work for compliance work is worth watching in 2027.
