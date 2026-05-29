---
type: Source
source_type: Security report
date_accessed: 2026-05-28
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[ivo-radic]]"
  - "[[pen-test-readout-2026-05-28]]"
  - "[[tenant-isolation-migration]]"
_organized: true
---

# Bracken Hollow Pen Test Report 2026

Penetration test report by [[ivo-radic]] of Bracken Hollow Security, testing from 2026-05-04 to 2026-05-15.

## Summary

- No cross-tenant data access achieved through the web app or API.
- One medium finding: verbose error messages in some API error responses. Fixed in QL-1561 on 2026-06-03, retested clean on 2026-06-10.
- Three informational items on security headers, fixed by 2026-06-20.

## Caveats

The vault records severity and fix only. The full report, with reproduction steps, stays in the SOC 2 evidence folder and is shared with customers only under NDA on request.

## Source Location

SOC 2 evidence folder, `Security testing/2026`, access restricted to engineering leads and [[colette-fairbanks]].
