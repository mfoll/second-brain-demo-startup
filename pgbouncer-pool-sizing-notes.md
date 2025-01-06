---
type: Note
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[pgbouncer-deployment-config]]"
_organized: true
---

# PgBouncer Pool Sizing Notes

Working notes on how big the PgBouncer pools in front of the [[primary-postgres-cluster]] should be now that the fold-back is done and only the shared database and Meridale's dedicated database remain.

## Current State

- Transaction mode since the [[pgbouncer-cutover-2026-04-14]].
- The reminder role keeps its reserved pool, as agreed after the [[reminder-outage-2026-03-17]].
- The extra pool entries for the three tenant instances were removed when those instances were deleted.

## Open Points

- The default pool was sized in April for about 50 databases. With two databases left it is generous, which is fine until a migration lane for a second enterprise tenant arrives.
- Kwabena's sizing worksheet and the numbers behind the April choice are in [[pgbouncer-pool-sizing-worksheet]]. Revisit before the next enterprise contract.

Configuration itself lives in [[pgbouncer-deployment-config]].
