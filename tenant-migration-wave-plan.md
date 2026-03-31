---
type: Source
source_type: Spreadsheet
date_accessed: 2026-03-02
belongs_to: "[[full-tenant-database-rollout]]"
related_to:
  - "[[adr-014-database-per-tenant]]"
_archived: true
_organized: true
---

# Tenant Migration Wave Plan

Archived. The spreadsheet that scheduled the move of about 280 tenants to their own databases, superseded with the [[full-tenant-database-rollout]] on 2026-06-11.

## Summary

Seventeen waves from 2026-03-02 to 2026-07-24, 10 to 20 tenants each, sorted by admin user count, with Meridale last. Columns: tenant ID, clinic type, admin users, row count, target instance, maintenance window, customer success owner, status. 48 rows reached "moved"; the rest never started.

## Caveats

The duration column assumed 15 minutes per tenant and nothing for migrations across tenants, which is the gap [[migration-fan-out]] describes.

## Source Location

Engineering shared drive, `Tenant isolation/wave-plan-2026`, sheet locked read-only since 2026-06-12.
