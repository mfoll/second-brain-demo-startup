---
type: Source
source_type: Internal document
date_accessed: 2026-09-30
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[on-call-handbook]]"
  - "[[connection-exhaustion]]"
_organized: true
---

# Alerting Rules Inventory

The list of every alert that can page, with threshold, owner and runbook link. Maintained by [[kwabena-asare]]; reviewed quarterly since the [[on-call-rotation-redesign]].

## Key Details

- 14 paging alerts as of 2026-09-30, down from 23 before the redesign; only customer-facing symptoms page.
- Reminder queue age over 10 minutes (added 2026-03-27, postmortem action 3).
- Primary connections over 70% of `max_connections`.
- API 5xx rate over 2% for 5 minutes.
- Pingrove 429 rate over 10% for 5 minutes (alert raised by Pingrove's own notice since 2026-04-02).
- Non-paging: disk, replica lag, certificate expiry, RLS coverage drop.

## Source Location

`quaylane-infra` repository, `monitoring/alerts.yaml`, with a generated table in `monitoring/README.md`.
