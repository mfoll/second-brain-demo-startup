---
type: Question
status: Superseded
belongs_to: "[[full-tenant-database-rollout]]"
related_to:
  - "[[connection-exhaustion]]"
  - "[[adr-019-isolation-by-contract-tier]]"
_organized: true
---

# Should Tenant Databases Live On The Primary Instance?

Asked during the pilot in 2026-01: put tenant databases on the existing primary (cheap) or on separate instances (isolated load and connections)?

## What Happened

We chose the primary for the pilot and early rollout to keep cost flat. The [[reminder-outage-2026-03-17]] answered it: one connection limit for everything. Tenant databases moved to three separate instances in 2026-04 and 2026-05.

## Superseded

By [[adr-019-isolation-by-contract-tier]]: only enterprise tenants get a database of their own, always on a separate instance.
