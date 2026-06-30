---
type: Source
source_type: Documentation
url: https://www.postgresql.org/docs/16/sql-createpolicy.html
publisher: The PostgreSQL Global Development Group
date_accessed: 2026-06-15
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[row-level-security]]"
  - "[[rls-policy-coverage-tracker]]"
_organized: true
---

# PostgreSQL 16 Documentation: CREATE POLICY

## Summary

Reference page for `CREATE POLICY`. A policy needs row security enabled on the table to apply. Existing rows are checked against the `USING` expression and new or updated rows against `WITH CHECK`; a row failing `USING` is simply invisible, while a row failing `WITH CHECK` raises an error. Policy names are per table, so one name can be reused across tables.

## Why It Matters

Our `tenant_isolation` policy uses both clauses so that a bug cannot insert a row into another tenant. The per-table naming lets [[bram-verhoef]]'s coverage query in [[rls-policy-coverage-tracker]] look for the same policy name on all 47 tables.

## Caveats

Reference only; performance of policies with subqueries is not covered here, and we learned it the slow way on `staff_room_links`.

## Source Links

- [CREATE POLICY](https://www.postgresql.org/docs/16/sql-createpolicy.html)
