---
type: Note
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[architecture-review-2025-11-18]]"
  - "[[grow-as-a-leader]]"
  - "[[reversals-should-be-cheap-and-public]]"
_organized: true
---

# Lessons From The Database-Per-Tenant Decision

My own notes, written in 2026-07 after the reversal. Not a postmortem; a reflection on how I made the call.

## What I Got Wrong

- **I answered a questionnaire instead of a customer.** The isolation questions in the [[meridale-security-questionnaire]] read like a demand for physical separation. Nobody asked [[samir-haddad]] what he would accept. When we did, in June, the answer was "a dedicated database for us".
- **I let warnings become future tasks.** [[kwabena-asare]] named both failure modes at [[architecture-review-2025-11-18]]. I wrote "mitigate during rollout" and put neither into the pilot's success criteria.
- **The pilot tested the easy part.** Moving one small tenant at a time was never the risk; running many databases at once was ([[pilot-retrospective-2026-02-27]]).
- **I treated an unfamiliar option as a risky one.** RLS lost in November mostly because none of us had run it.

## What I Got Right

- The decision was written down with its reasons ([[adr-014-database-per-tenant]]), which made the reversal a conversation about evidence.
- We kept the tooling. It paid for itself with Meridale.

## What I Do Differently

- Big decisions name their review trigger and kill criteria up front.
- Concerns raised in a review become pilot success criteria or are explicitly accepted, in writing, by me.
- Ask the customer before designing for the questionnaire.
