---
type: Note
belongs_to: "[[seed-extension-diligence]]"
related_to:
  - "[[architecture-review-2026-06-11]]"
  - "[[tell-investors-the-bad-news-before-the-data-room-does]]"
  - "[[tenant-isolation-migration]]"
_organized: true
---

# Explaining The Tenant Reversal To Investors

My preparation for telling the story out loud on the diligence call of 2026-08-19; the written one-pager Arun received beforehand is [[tenant-isolation-explainer-for-diligence]]. Kept because the same story comes up with every enterprise prospect too.

## The Story in Five Sentences

1. In 2025 a large clinic group asked how we isolate tenants, and our honest answer was application code only ([[meridale-security-questionnaire]]).
2. On 2025-11-18 we decided to give every tenant its own PostgreSQL database ([[architecture-review-2025-11-18]]).
3. After 48 tenants, schema migrations took 2 h 40 min across databases, RDS cost rose by $3,100 a month, and a migration batch caused our worst outage ([[reminder-outage-2026-03-17]]).
4. On 2026-06-11 we kept dedicated databases for enterprise contracts, where customers require and pay for them, and moved everyone else to row-level security in the shared database ([[architecture-review-2026-06-11]]).
5. Meridale has had its own database since 2026-08-21; an independent pen test found no cross-tenant access in the shared schema ([[bracken-hollow-pen-test-report-2026]]).

## Questions I Expected

- "Was the first decision a mistake?" Partly. The requirement was real; applying it to all 280 tenants was not needed. We should have asked which customers required it.
- "Is row-level security enough?" It is a database-enforced control, unlike what we had in 2025. It does not protect against a superuser or a role with bypass rights; we restrict those ([[row-level-security]]).
- "Will it change again?" Only if non-enterprise customers start requiring dedicated storage.

## What Actually Happened

Arun asked the first two and accepted the answers. See [[technical-diligence-call-2026-08-19]].
