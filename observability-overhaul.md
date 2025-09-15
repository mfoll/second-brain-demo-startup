---
type: Project
status: Paused
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[kwabena-asare]]"
  - "[[opentelemetry-docs-javascript]]"
has:
  - "[[tracing-spike-notes-2025-09]]"
  - "[[observability-pause-decision-2026-04-06]]"
  - "[[when-do-we-resume-the-observability-overhaul]]"
_organized: true
---

# Observability Overhaul

Replace our mix of log searches and ad hoc dashboards with distributed tracing across the API and the job workers, so that the next incident does not start with forty minutes of guessing.

## Outcome

Distributed tracing with OpenTelemetry across the API and workers. Paused 2026-04-06 to free time for SOC 2 work; resumption planned for 2027-Q1.

## Current State

- Paused since 2026-04-06, see [[observability-pause-decision-2026-04-06]].
- Done: OpenTelemetry tracing in `quaylane-api` for about 70% of routes, exported to a hosted tracing backend on a free tier; PostgreSQL query spans on.
- Not done: the workers in `quaylane-workers`, trace context through the Redis queue, and any sampling policy beyond 10% head sampling.
- Resume condition: SOC 2 Type II observation running smoothly and a named owner with half their time for six weeks.

## Scope and Boundaries

Traces and the metrics derived from them. Logging stays as it is. Alert rules are tracked in [[alerting-rules-inventory]] and are not part of this project. Browser tracing is out: the [[opentelemetry-docs-javascript]] page lists browser instrumentation as experimental.

## Working Context

- The spike in 2025-09 is in [[tracing-spike-notes-2025-09]]: auto-instrumentation for HTTP and `pg` worked in a day; propagating context through queue jobs needs our own code.
- The March outage would have been diagnosed faster with worker traces: we spent the first 40 minutes looking at Pingrove because that is where the errors were visible.
- [[kohyarnejadfard-2022-anomaly-detection-microservice-tracing]] and [[xing-2025-microservice-anomaly-detection-fault-localization]] are interesting but far beyond what we need. We need traces first.
- [[small-teams-should-buy-observability]] is my stance on build versus buy.

## Next Actions

- [ ] Write the restart plan (owner, six-week scope, worker propagation design) before 2027-01-04.
- [ ] Price the paid tier of the tracing backend at full volume for [[engineering-budget-2027]].
- [ ] Keep the API instrumentation working: one smoke test in CI checks that a span is emitted.

## Open Questions

- [[when-do-we-resume-the-observability-overhaul]]

## Important Notes

- [[tracing-spike-notes-2025-09]]
- [[observability-pause-decision-2026-04-06]]
- [[wikipedia-observability-software]]

## Do Not Do Yet

> [!danger]
> Do not turn on tracing in the workers piecemeal before the queue propagation design exists: half-connected traces were worse than none in the spike.

## Maintenance Log

- 2026-04-06: Paused to free Kwabena for SOC 2 evidence work.
- 2026-01-19: API tracing at about 70% of routes.
- 2025-11-03: First traces in production.
- 2025-09-01: Project started with a two-week spike.
