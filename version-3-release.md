---
type: Project
status: Completed
start: 2026-01-05
end: 2026-09-15
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[appointment-scheduling]]"
  - "[[meridale-enterprise-rollout]]"
  - "[[tenant-isolation-migration]]"
has:
  - "[[waitlist-autofill]]"
  - "[[multi-location-calendars]]"
  - "[[enterprise-sso]]"
  - "[[release-planning-2026-06-02]]"
  - "[[version-3-release-plan]]"
_organized: true
---

# Version 3 Release

Umbrella for Quaylane 3.0: waitlist autofill, multi-location calendars and enterprise SSO, the release that turned us from a single-clinic tool into something a clinic group could buy. Planned for 2026-06-23, shipped 2026-09-15.

## Outcome

Quaylane 3.0 generally available to all clinic accounts. Reached on 2026-09-15 for all about 280 accounts, with SSO already live for Meridale since 2026-06-30.

## Current State

- Completed. 3.0 GA on 2026-09-15; 3.0.4 is the current patch release as of 2026-10-20.
- Adoption after five weeks: waitlist autofill enabled by 96 accounts, multi-location calendars used by 31 of the 34 accounts with more than one site. Numbers from the [[product-usage-dashboard]].
- No open release blockers. Follow-up work (waitlist offers by email, a cross-site room report) moved into [[roadmap-2027]].

## Scope and Boundaries

Three features, each with its own child Project and owner:

- [[waitlist-autofill]]: Hamish Pettigrew, with Ayesha Qureshi from 2026-04.
- [[multi-location-calendars]]: Lucia Ferreyra, with design by Mai Nakagawa.
- [[enterprise-sso]]: Min-jae Oh, with Kwabena Asare on the infrastructure side.

Out of scope from the start: online booking by patients (now [[online-booking-widget]]), native calendar sync, and anything in the tenant isolation work, which ran under [[run-the-platform]].

## Working Context

The plan in [[version-3-release-plan]] assumed all five engineers on product work from March, plus the first 2026 hire from April. In practice the [[tenant-isolation-migration]] and the clean-up after the [[reminder-outage-2026-03-17]] took Teodora and Kwabena for 11 weeks. By late May the calendars work was about five weeks behind and SSO had a contractual date of 2026-07-01 that could not move.

At [[release-planning-2026-06-02]] we moved the 3.0 date to 2026-09-15 and split SSO out to ship alone by 2026-06-30. Options we rejected: cutting multi-location calendars from 3.0 (Meridale needed it for the rollout), and shipping on 2026-06-23 behind feature flags with an unfinished calendar (Felix and Lucia both said the half-built calendar would generate more support load than it saved). The reasoning is in [[lessons-from-the-version-3-slip]].

SSO went live on 2026-06-30, one day ahead of the contract date. Waitlist autofill finished on 2026-08-28 after a 14-clinic beta. Calendars finished on 2026-09-04. GA followed on the train of 2026-09-15.

## Active Workflows

- Release train every second Tuesday, run by Lucia since 2026-07 following [[cut-a-release]].
- Feature flags listed in [[feature-flag-inventory-v3]]; flags for 3.0 features are scheduled for removal by 2026-11-30.

## Next Actions

- [ ] Remove the 3.0 feature flags by 2026-11-30 (Lucia).
- [ ] Share [[lessons-from-the-version-3-slip]] at the engineering meeting of 2026-11-04.

## Open Questions

- [[should-release-dates-be-promised-to-customers]]
- [[should-v3-ship-without-sso]] (superseded by the 2026-06-02 decision)

## Important Notes

- [[release-planning-2026-06-02]]
- [[version-3-general-availability-2026-09-15]]
- [[version-3-release-notes]]
- [[lessons-from-the-version-3-slip]]

## Maintenance Log

- 2026-09-15: GA for all accounts. Project closed.
- 2026-06-30: SSO live for Meridale ahead of 2026-07-01.
- 2026-06-02: Date moved from 2026-06-23 to 2026-09-15; SSO split out.
- 2026-01-05: Scope agreed at [[version-3-scope-meeting-2026-01-05]].
