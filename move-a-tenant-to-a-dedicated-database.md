---
type: Procedure
belongs_to: "[[enterprise-dedicated-databases]]"
related_to:
  - "[[tenant-migration-tooling]]"
  - "[[when-should-a-tenant-get-a-dedicated-database]]"
  - "[[enterprise-database-terraform-module]]"
_organized: true
---

# Move A Tenant To A Dedicated Database

Runbook for giving an enterprise tenant its own RDS instance. Used once in production, for Meridale on 2026-08-21. Derived from the pilot runbook of 2026-01.

## Preconditions

- The contract requires a dedicated database (see [[when-should-a-tenant-get-a-dedicated-database]]). Engineering does not move tenants on request alone.
- Approval from me and a change log entry.
- A maintenance window agreed with the customer through customer success, at least 5 business days ahead.

## Steps

1. Create the instance from the [[enterprise-database-terraform-module]]: `module "ent_<name>"`, own KMS key, Multi-AZ, backups 35 days. Merge and apply through the normal pipeline.
2. Add a PgBouncer pool for the new database and deploy PgBouncer.
3. Dry run: `tenantctl move --tenant <id> --target ent-<name> --dry-run` against a restored snapshot. Note the duration.
4. In the window: put the tenant in read-only mode (`tenantctl freeze`), run `tenantctl move`, then `tenantctl verify` (row counts per table, sequences, RLS policies present, schema version).
5. Switch the tenant's routing entry in `tenant_directory` and unfreeze.
6. Smoke test as a test admin user of that tenant: open the calendar, create and cancel a test appointment, trigger a test reminder to an internal number.
7. Keep the tenant's rows in the shared database for 14 days, frozen, then delete them with `tenantctl purge` and a second engineer watching.

## Rollback

Until step 7, rollback is switching `tenant_directory` back and unfreezing. Meridale's move took 48 minutes including smoke tests; the rollback was rehearsed and took 6.

## Verification

Record the move in the [[incident-log]] as a planned change and add the instance to the [[soc2-control-matrix]] asset list.
