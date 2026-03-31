---
type: Source
source_type: Documentation
url: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Limits.html
publisher: Amazon Web Services
date_accessed: 2026-03-18
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[connection-exhaustion]]"
_organized: true
---

# Quotas and constraints for Amazon RDS

## Summary

AWS documentation of RDS quotas, including a table of maximum database connections per engine. For PostgreSQL, `max_connections` accepts 6 to 262143 and defaults to `LEAST({DBInstanceClassMemory/9531392}, 5000)`, so the limit scales with instance memory and is capped at 5,000 by default.

## Why It Matters

Explains the 3,276 limit we hit on 2026-03-17 on a db.r6g.xlarge ([[primary-postgres-cluster]]). It also means that moving to a larger instance would only have bought headroom, not fixed the multiplication; [[kwabena-asare]] made that point at [[postmortem-review-2026-03-24]].

## Caveats

The exact value depends on `DBInstanceClassMemory`, which is less than the nominal instance memory. We read the effective value from the instance, not from the formula.

## Source Links

- [Quotas and constraints for Amazon RDS](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_Limits.html)
