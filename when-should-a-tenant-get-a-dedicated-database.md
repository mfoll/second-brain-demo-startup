---
type: Question
status: Answered
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[adr-019-isolation-by-contract-tier]]"
  - "[[enterprise-dedicated-databases]]"
  - "[[dana-prescott]]"
_organized: true
---

# When Should A Tenant Get A Dedicated Database?

## Current Answer

> [!info]
> Only when an enterprise contract requires it and pays for it: a separate RDS instance with its own key, about $750 a month at current sizing. Not on request, not as a sales sweetener, not for size alone.

Working criteria agreed with [[dana-prescott]] and [[renata-castellano]] on 2026-07-15:

- Contract annual value above $100,000, or a written isolation requirement from the customer's security review that RLS cannot meet.
- The cost appears in the pricing.
- Engineering signs off before Sales mentions it.

## Why

[[adr-019-isolation-by-contract-tier]]. Every dedicated database adds a migration lane and an instance to monitor.

## Still Unsettled

Whether a large clinic group without an enterprise contract can buy it as an add-on. No one has asked yet.
