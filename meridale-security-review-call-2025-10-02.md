---
type: Event
date: 2025-10-02
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[meridale-security-questionnaire]]"
  - "[[samir-haddad]]"
  - "[[multi-tenancy]]"
_organized: true
---

# Meridale Security Review Call 2025-10-02

A one-hour call with [[samir-haddad]] of Meridale Clinic Group to go through our draft answers to the [[meridale-security-questionnaire]] before we sent the final version. On our side: me, [[teodora-vasilescu]] and [[dana-prescott]].

## What Happened

- Samir spent 40 of the 60 minutes on tenant isolation. His core question: if a developer forgets the `tenant_id` filter in one query, what stops a front-desk user at one clinic from seeing another clinic's appointment book? Our honest answer was code review and tests. He said that was an application control and asked whether we had a database control.
- He asked whether Meridale could have its own database with its own encryption key. We said we would look at it.
- On audit: he did not expect a SOC 2 report from a company our size during the pilot, but said Meridale's board would require one for a group-wide contract.
- Ten minutes on SSO: Meridale staff turnover at the front desk is high, and he wants deprovisioning to happen in their directory, not by emailing us.

## Decisions and Follow-ups

- We corrected two draft answers that overstated isolation ([[meridale-questionnaire-draft-answers-2025-10]]) before sending the final version on 2025-10-10.
- I asked Teodora to write an isolation options paper for an architecture review; that became [[architecture-review-2025-11-18]].
- Dana took SSO and SOC 2 as likely contract conditions to Renata.

## Reflection

I went into the call thinking of the questionnaire as a sales hurdle. I came out of it seeing that Samir had described a real gap in how we protected tenants, and that "we review code carefully" is not an answer a security manager can verify.
