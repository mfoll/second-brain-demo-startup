---
type: Concept
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[transaction-pooling]]"
  - "[[wikipedia-connection-pool]]"
_organized: true
---

# Connection Exhaustion

When clients ask a PostgreSQL server for more connections than its `max_connections` setting allows, new connections fail with "too many clients", and whatever needed one stops working. Each PostgreSQL connection is a server process with its own memory, so the limit is real and not something to raise casually ([[postgresql-docs-connections-and-authentication]]).

## Why It Hit Us

- On RDS the limit comes from the instance memory; our db.r6g.xlarge resolves to 3,276 ([[amazon-rds-docs-quotas-and-constraints]]).
- Application pools are per process and per database. With a database per tenant, total connections grew with the number of tenants times the number of processes.
- Nothing reserved capacity for critical work, so a migration batch starved the reminder workers on 2026-03-17.

## Defenses We Now Use

- PgBouncer in [[transaction-pooling]] mode, so many client connections share few server connections.
- A reserved pool for the reminder role.
- A throttle on batch jobs and migrations.
- An alert at 70% of `max_connections`, listed in [[alerting-rules-inventory]].

See also [[wikipedia-connection-pool]].
