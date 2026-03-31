---
type: Source
source_type: Documentation
url: https://www.postgresql.org/docs/16/runtime-config-connection.html
publisher: The PostgreSQL Global Development Group
date_accessed: 2026-03-18
belongs_to: "[[reminder-outage-postmortem]]"
related_to:
  - "[[connection-exhaustion]]"
  - "[[primary-postgres-cluster]]"
_organized: true
---

# PostgreSQL 16 Documentation: 20.3. Connections and Authentication

## Summary

Manual section on connection settings. `max_connections` sets the maximum number of concurrent connections, typically 100 by default, and can only be changed at server start. The section also covers `reserved_connections` and `superuser_reserved_connections`, which hold slots back for privileged roles.

## Why It Matters

Read the day after the [[reminder-outage-2026-03-17]]. Raising `max_connections` needs a restart and costs memory per connection, so it was not the fix. The reserved-slot idea inspired postmortem action 6, though we implemented it with a dedicated PgBouncer pool for the reminder role rather than a server setting.

## Caveats

On RDS the default comes from the instance class formula instead; see [[amazon-rds-docs-quotas-and-constraints]].

## Source Links

- [20.3. Connections and Authentication](https://www.postgresql.org/docs/16/runtime-config-connection.html)
