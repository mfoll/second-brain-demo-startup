---
type: Source
source_type: Code repository
date_accessed: 2026-09-09
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[move-a-tenant-to-a-dedicated-database]]"
  - "[[teodora-vasilescu]]"
_organized: true
---

# Tenant Migration Tooling

`tenantctl`, the command-line tool in `quaylane-infra/tools/tenantctl` that moves, verifies and migrates tenant databases. Owner: [[teodora-vasilescu]].

## Summary

Subcommands: `freeze`, `move`, `verify`, `migrate`, `purge`. Written in TypeScript, runs from the deploy pipeline with a dedicated role. Built for the [[database-per-tenant-pilot]] and kept after the reversal for enterprise moves.

## Key Details

- `verify` checks row counts per table, sequence values, presence of RLS policies and schema version. Sequence checks were added after the failed pilot move of tenant 1102.
- `migrate` enforces the throttle from postmortem action 2 (4 databases, 8 connections each) unless `--override` is passed with a change log reference.
- `move` works between databases on one instance or across instances since 2026-07.

## Source Location

`quaylane-infra` repository, `tools/tenantctl`, with its README and runbook links.
