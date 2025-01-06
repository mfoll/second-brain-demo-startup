---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[ayesha-qureshi]]"
_organized: true
---

# Reliability Reading List

What I give a new engineer joining the on-call rotation, in order. Started for [[ayesha-qureshi]] in 2026-04.

1. [[reminder-outage-2026-03-17]] and [[postmortem-review-2026-03-24]]: our own worst day first.
2. [[run-an-incident]] and [[on-call-handbook]].
3. [[reminder-pipeline-overview]] and [[infrastructure-map]].
4. [[connection-exhaustion]] and [[transaction-pooling]], with [[pgbouncer-docs-features]].
5. [[wikipedia-site-reliability-engineering]] and [[wikipedia-service-level-objective]] for vocabulary.
6. [[wikipedia-thundering-herd-problem]] and [[wikipedia-exponential-backoff]], because retry storms will happen again somewhere.
7. [[row-level-security]], so nobody "fixes" a zero-row result by using the reporting role.

Optional: [[kohyarnejadfard-2022-anomaly-detection-microservice-tracing]], for curiosity rather than practice.
