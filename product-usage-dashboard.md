---
type: Source
source_type: Internal dashboard
date_accessed: 2026-10-20
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[version-3-release]]"
  - "[[no-show-rate]]"
_organized: true
---

# Product Usage Dashboard

The product analytics dashboard built on the read replica: active accounts, feature adoption, reminders sent and aggregate no-show rates.

## Summary

- Weekly active accounts: 268 of about 280 in 2026-10.
- Waitlist autofill enabled by 96 accounts five weeks after GA; cross-site view used by 31 of 34 multi-site accounts.
- Reminders sent: about 410,000 a month.

## Why It Matters

Adoption numbers for [[version-3-release]] and the segment counts in [[clinic-segments-overview]] come from here. It is also where clinics' aggregate [[no-show-rate]] is computed for the in-app report.

## Key Details

- All metrics are aggregates per account or per site. No panel shows a person.
- Refreshed nightly at 03:00.

## Caveats

"Active" means any admin login in the week, which overstates engagement for small accounts.

## Source Location

Metabase, collection "Product", maintained by Felix and Teodora. Queries run against the read replica of the [[primary-postgres-cluster]].
