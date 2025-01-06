---
type: Person
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[row-level-security-rollout]]"
  - "[[engineering-hiring-2026]]"
  - "[[platform-engineering]]"
_organized: true
---

# Bram Verhoef

Engineer, platform. Joined on 2026-07-06, the second hire of [[engineering-hiring-2026]].

## Role

Bram was hired to take infrastructure load off [[kwabena-asare]] and to own the database work after the reversal. He came from a mid-size e-commerce company where he ran their PostgreSQL upgrades. He splits his time roughly half platform, half product tickets on the API.

## How We Work Together

- Biweekly one-to-one, plus a short Friday check-in during his first three months.
- He asks good "why is this here" questions about `quaylane-infra`; several of them turned into fixes in [[infrastructure-map]].
- He likes clear written specs. The RLS coverage list in [[rls-policy-coverage-tracker]] was his idea.

## Current Threads

- Day-to-day owner of the [[row-level-security-rollout]]: 41 of 47 tables covered, the partitioned `audit_events` table next.
- Ran most of the fold-back of the 48 tenants with [[teodora-vasilescu]] in his first eight weeks ([[fold-back-complete-2026-08-28]]).
- In the on-call rotation since 2026-09.

## Notes

He is not a "platform engineer" in the sense of the open 2027 question: his role is half product by design. Keep that distinction clear when the hiring decision is discussed.

## Links

[[run-the-platform]], [[primary-postgres-cluster]].
