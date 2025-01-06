---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[bram-verhoef]]"
  - "[[infrastructure-map]]"
  - "[[olu-ajayi]]"
_organized: true
---

# Platform Onboarding Guide

First two weeks for an engineer who will touch infrastructure. Written for [[bram-verhoef]] in 2026-07 and reused, in a shorter form, for [[olu-ajayi]].

## Week 1

- Read [[infrastructure-map]], [[primary-postgres-cluster]] and [[reliability-reading-list]].
- Pair with [[kwabena-asare]] on one Terraform change from pull request to apply.
- Get staging access; production read-only access is granted after the access review, per the [[soc2-control-matrix]].

## Week 2

- Run a staging schema migration with [[run-a-schema-migration]].
- Shadow the on-call primary for two days.
- Write one RLS policy with a pgTAP test, reviewed by [[teodora-vasilescu]].

## Rules

Never connect to production from a laptop with a write role. Never paste tenant data into chat, tickets or this vault; use counts and tenant IDs.
