---
type: Project
status: Active
start: 2026-05-04
belongs_to: "[[support-the-company]]"
related_to:
  - "[[renata-castellano]]"
  - "[[arun-velayudhan]]"
  - "[[margot-ellison]]"
has:
  - "[[technical-diligence-call-2026-08-19]]"
  - "[[copperwell-diligence-request-list]]"
  - "[[seed-extension-data-room]]"
  - "[[what-should-the-scheduling-engine-bus-factor-be]]"
_organized: true
---

# Seed Extension Diligence

The engineering side of Quaylane's $2.5M seed extension: answering technical diligence for the investors, mainly Copperwell Capital, and getting the round to close. [[renata-castellano]] leads the round; I own the technical answers.

## Outcome

Technical diligence answered with no open engineering conditions, and the round closed (expected 2026-11-20).

## Current State

- Round: $2.5M. Larchgate Ventures $1.2M, Copperwell Capital $1.0M (new investor), angels $0.3M including [[wendell-price]]. Terms as shared with the team on 2026-10-01; detail stays in the [[seed-extension-data-room]].
- Term sheet signed 2026-09-30 ([[term-sheet-signed-2026-09-30]]). Close expected 2026-11-20.
- Technical diligence call with [[arun-velayudhan]] on 2026-08-19 ([[technical-diligence-call-2026-08-19]]). All 34 items on the [[copperwell-diligence-request-list]] answered by 2026-09-12.
- Two follow-ups from the call: a recorded walkthrough of the scheduling engine (done 2026-09-09, by Teodora) and a pairing rotation on it (running since 2026-09-14). Arun wants a status line on the rotation before close.

## Scope and Boundaries

Engineering diligence only: architecture, security, reliability, team, costs. The financial model belongs to Renata and [[gwen-talbot]]; the cap table and side letters are not mine to read or record. I write answers into the data room and keep only pointers and decisions here.

## Working Context

The hard question was the tenant isolation reversal. An investor reading "we decided per-tenant databases, then reversed after 48 tenants" could see churn in the architecture. I prepared the story ahead of the call ([[explaining-the-tenant-reversal-to-investors]]): the requirement was a contract term for enterprise customers, we met it for Meridale, and we stopped paying the fan-out cost for 230 small clinics that never asked for it. Arun accepted that and asked for the pen test summary as evidence that the shared database is isolated ([[bracken-hollow-pen-test-report-2026]]).

Cloud cost per clinic, $14 a month in July 2026, came up as a margin question ([[cloud-cost-per-clinic]]). The bus factor on the scheduling engine was the only point where I had no good answer: [[teodora-vasilescu]] and I were the only people who knew it well.

## Next Actions

- [ ] Send Arun the pairing rotation status (who has paired on the engine, which modules) by 2026-11-06.
- [ ] Confirm with Renata that no engineering item is listed as a closing condition.
- [ ] After close, move the two follow-ups into [[lead-engineering-team]] as ordinary team practice.

## Open Questions

- [[what-should-the-scheduling-engine-bus-factor-be]]
- [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]], since the extension funds two engineering hires in 2027.

## Important Notes

- [[technical-diligence-call-2026-08-19]]
- [[copperwell-diligence-request-list]]
- [[seed-extension-kickoff-2026-05-04]]
- [[technical-diligence]]

## Maintenance Log

- 2026-09-30: Term sheet signed.
- 2026-09-12: Last diligence request answered.
- 2026-08-19: Technical diligence call with Arun Velayudhan.
- 2026-05-04: Extension opened; technical diligence assigned to me.
