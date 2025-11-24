---
type: Opinion
status: Active
confidence: High
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[adr-019-isolation-by-contract-tier]]"
_organized: true
---

# Isolation Should Follow The Contract

## Stance

The isolation a tenant gets should be the isolation its contract requires and pays for, not the strongest model we can imagine. Defense in depth inside a shared database (application filters plus RLS) is the default; physical separation is a product feature with a price.

## Scope

B2B SaaS of our size, with one or two engineers able to work on infrastructure. A regulated customer base might change the default.

## Why I Think This

- In November 2025 I chose the strongest model out of fear of one questionnaire. It cost $3,100 a month, 2 h 40 min migrations and an outage ([[full-tenant-database-rollout]]).
- When we finally asked, Meridale wanted separation for Meridale, not for everyone ([[architecture-review-2026-06-11]]).
- Theo Mallory and the pen test both pointed to enforcement, not separation, as the real gap.

## What Would Change My Mind

A security review we lose because of RLS, or a cross-tenant data incident in the shared database.

## Implications

Sales asks engineering before promising isolation. See [[when-should-a-tenant-get-a-dedicated-database]].
