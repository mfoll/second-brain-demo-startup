---
type: Source
source_type: Documentation
url: https://www.postgresql.org/docs/16/ddl-rowsecurity.html
publisher: The PostgreSQL Global Development Group
date_accessed: 2026-06-15
belongs_to: "[[row-level-security-rollout]]"
related_to:
  - "[[row-level-security]]"
  - "[[postgresql-docs-create-policy]]"
_organized: true
---

# PostgreSQL 16 Documentation: 5.8. Row Security Policies

## Summary

The PostgreSQL manual's chapter on row security. Points we rely on: with row security enabled, row access must be allowed by a policy, and if no policy exists a default-deny applies; whole-table operations such as `TRUNCATE` are not subject to row security; superusers and roles with `BYPASSRLS` always bypass it; table owners normally bypass it unless the table is altered with `FORCE ROW LEVEL SECURITY`.

## Why It Matters

This page is why every migration in the [[row-level-security-rollout]] has both `ENABLE` and `FORCE`: our application role owns the tables. It is also the reference for what RLS does not protect, which [[teodora-vasilescu]] insisted go into [[row-level-security]] verbatim in our own words before anyone told a customer about it.

## Caveats

Version 16 page; check the matching version when we upgrade to 17.

## Source Links

- [5.8. Row Security Policies](https://www.postgresql.org/docs/16/ddl-rowsecurity.html)
