---
type: Question
status: Open
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[rls-policy-coverage-tracker]]"
  - "[[bram-verhoef]]"
_organized: true
---

# Can We Reach Full RLS Coverage This Year?

41 of 47 tenant-scoped tables are covered on 2026-10-23. Can the last 6 be done by 2026-12-18 without slowing version 3.1 work?

## What We Know

- `staff_room_links` and `import_batches` need a `tenant_id` column first: about a week together.
- `audit_events` needs policies on 24 partitions and automation for new ones: [[bram-verhoef]] estimates 4 days.
- The two report tables might become views over covered tables instead (2 days) or keep a reporting-only role.
- `waitlist_offers_archive` is straightforward.

## What Would Answer It

Bram's estimate holds and the [[roadmap-2027]] planning does not take him in November. I will check on 2026-11-16.
