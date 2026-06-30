---
type: Source
source_type: Internal test record
date_accessed: 2026-06-30
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[scim-deprovisioning]]"
  - "[[soc2-control-matrix]]"
_organized: true
---

# SCIM Deprovisioning Test Log

Record of the deprovisioning tests run with Meridale's test tenant on 2026-06-12 and repeated in production on 2026-06-30.

## Summary

- Five test users disabled at Meridale's identity provider; all lost access in Quaylane in 64 to 131 seconds.
- Active sessions ended on the next request in all five cases.
- One `DELETE` and four `active: false` updates, matching the two methods in [[scim-protocol-rfc-7644]].

## Why It Matters

It is evidence for the offboarding row of the [[soc2-control-matrix]] for SSO customers and for Meridale's own security review.

## Key Details

- Audit events written for every change, with the IdP's request ID.
- Timing is set by how often the IdP pushes changes, not by our side, which processes in under a second.

## Caveats

Tested with one identity provider only. Each new SSO customer gets the same test at setup.

## Source Location

SOC 2 evidence folder, `Change and access/SSO/SCIM tests 2026-06`; summary table in the SSO runbook in `quaylane-api/docs/`.
