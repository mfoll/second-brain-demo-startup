---
type: Source
source_type: Internal document
date_accessed: 2026-06-24
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[run-an-incident]]"
  - "[[abigail-ferris]]"
_organized: true
---

# Security Incident Response Plan

The plan for suspected security incidents, approved 2026-06-24. It extends the availability runbook ([[run-an-incident]]), which the readiness review found did not cover breaches or suspected data exposure.

## What It Adds

- A security severity scale separate from availability: S1 confirmed exposure of customer data, S2 suspected exposure or compromised credential, S3 policy violation without exposure.
- Roles: incident commander as in the availability runbook; Nikolas always involved for S1 and S2; Renata informs customers; [[abigail-ferris]] advises on notification duties under the data protection law and customer contracts.
- Evidence preservation before cleanup: snapshots, log exports, access records.
- Customer notification: contract timelines tracked in a table per enterprise customer; Meridale's is 48 hours from confirmation.

## Status

Tabletop exercise held 2026-07-15 with a scenario of a leaked staff session token. No real S1 or S2 incident to date.

## Source Location

Shared drive, `Security/Policies/security-incident-response-plan.pdf`.
