---
type: Concept
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[pgbouncer-docs-features]]"
  - "[[row-level-security]]"
  - "[[connection-exhaustion]]"
_organized: true
---

# Transaction Pooling

A PgBouncer mode in which a server connection is lent to a client only for the length of one transaction, then returned to the pool. It is the most useful mode for a web app with many short transactions, and the one that breaks session state.

## Trade-off

- Gain: thousands of client connections can share a few dozen server connections. Our primary went from about 1,500 to about 160 server connections at peak ([[pgbouncer-cutover-2026-04-14]]).
- Cost: anything that lives in the session rather than the transaction can leak to another client or vanish. The [[pgbouncer-docs-features]] page lists session `SET`, `LISTEN`, `WITH HOLD` cursors and SQL-level `PREPARE` among the features that do not work.

## Rules in Our Code

- Use `SET LOCAL` or `set_config(..., true)`, never plain `SET`.
- No `LISTEN` through PgBouncer; the one job that needs it connects directly with its own small limit.
- The tenant setting for [[row-level-security]] is transaction-scoped by design, which is why RLS and transaction pooling fit together.
