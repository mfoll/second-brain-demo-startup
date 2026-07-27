---
type: Source
source_type: Code repository
date_accessed: 2026-07-20
belongs_to: "[[enterprise-dedicated-databases]]"
related_to:
  - "[[kwabena-asare]]"
  - "[[move-a-tenant-to-a-dedicated-database]]"
_organized: true
---

# Enterprise Database Terraform Module

`modules/enterprise_db` in `quaylane-infra`, merged on 2026-07-20 (QL-1688). Written by [[kwabena-asare]].

## Key Details

- Creates an RDS for PostgreSQL 16 instance (default db.r6g.large, Multi-AZ), a dedicated KMS key with a key policy limited to the production database role, a parameter group matching the primary, 35-day backups, and alarms on CPU, storage and connections.
- Adds the instance to the PgBouncer configuration through an output consumed by the PgBouncer module.
- One module instance per enterprise tenant; today only `ent_meridale`.

## Source Location

`quaylane-infra` repository, `terraform/modules/enterprise_db`.
