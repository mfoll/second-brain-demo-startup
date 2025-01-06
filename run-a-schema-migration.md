---
type: Procedure
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[migration-fan-out]]"
  - "[[row-level-security]]"
  - "[[teodora-vasilescu]]"
_organized: true
---

# Run A Schema Migration

How to change the production schema without repeating the [[reminder-outage-2026-03-17]]. Owner: [[teodora-vasilescu]].

## Before

1. The migration lives in `quaylane-api/migrations` and goes through a normal pull request with one recorded approval.
2. Any new tenant-scoped table includes `tenant_id`, `ENABLE` and `FORCE ROW LEVEL SECURITY` and the `tenant_isolation` policy in the same migration, plus a pgTAP test. See [[row-level-security]].
3. Long operations (index builds, backfills over 1 million rows) are split: `CREATE INDEX CONCURRENTLY` in its own migration, backfills as batched jobs.
4. Run against the staging copy and note the duration in the pull request.

## Running

1. Migrations run from the deploy pipeline, never from a laptop.
2. Window: outside 07:00 to 19:00 on weekdays for anything over 2 minutes in staging.
3. Order: shared database first, then each enterprise database in its own lane (today only `ent-meridale`), through `tenantctl migrate --lane enterprise`.
4. Throttle (postmortem action 2): at most 4 databases in parallel, at most 8 connections each. The tool refuses higher values without `--override`, which requires a change log entry.
5. Watch the connection panel and reminder queue age while it runs. If queue age passes 5 minutes, stop the migration.

## After

- Confirm schema version on every database with `tenantctl verify --schema`.
- Record duration in [[schema-migration-timing-log]].

## Why the Rules Exist

Fan-out across many databases multiplies connections and time ([[migration-fan-out]]). Under the old model a migration took 2 h 40 min across 49 databases; now it takes 6 to 12 minutes across two.
