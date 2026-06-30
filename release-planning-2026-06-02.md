---
type: Event
date: 2026-06-02
belongs_to: "[[version-3-release]]"
related_to:
  - "[[enterprise-sso]]"
  - "[[multi-location-calendars]]"
  - "[[lessons-from-the-version-3-slip]]"
_organized: true
---

# Release Planning 2026-06-02

The meeting where Quaylane 3.0 moved from 2026-06-23 to 2026-09-15 and SSO was split out to ship on its own by 2026-06-30.

## At a Glance

> [!note]
> Decision: 3.0 GA moves to 2026-09-15. Enterprise SSO ships alone, behind a per-organization flag, on the train of 2026-06-30, one day before Meridale's contractual date of 2026-07-01. Customers hear the new date from Felix and Imani by 2026-06-05.

Present: Felix Ostrowski, Lucia Ferreyra, Min-jae Oh, Hamish Pettigrew, Mai Nakagawa, Imani Brooks, Renata Castellano (last 20 minutes), me.

## Context

The plan in [[version-3-release-plan]] assumed all five engineers on product work from March, plus the first 2026 hire from April. Between 2026-02 and 2026-05 the [[tenant-isolation-migration]] and the clean-up after the [[reminder-outage-2026-03-17]] took Teodora and Kwabena for 11 weeks, and pulled Hamish for two weeks on the postmortem actions. Status on 2026-06-02:

- [[enterprise-sso]]: functionally done, testing with Meridale's test tenant. On track for the end of June.
- [[waitlist-autofill]]: in beta with 14 clinics since 2026-05-11. Needed about six more weeks of beta for the edge cases.
- [[multi-location-calendars]]: about five weeks behind. The 40-site view took 4.8 s at p95 and the site move flow was not built.

## Options considered

1. **Ship 3.0 on 2026-06-23 with calendars behind a flag.** Rejected. Lucia and Felix both expected a half-built calendar to generate more support load than it saved, and Meridale's waves needed the finished version anyway.
2. **Ship 3.0 on 2026-06-23 without multi-location calendars.** Rejected. The Meridale rollout depends on it; a 3.0 without it is a release in name only. See also [[should-v3-ship-without-sso]], the earlier version of this argument.
3. **Move everything to September, SSO included.** Rejected immediately: the 2026-07-01 SSO date is contractual.
4. **Move 3.0 to 2026-09-15 and ship SSO alone by 2026-06-30.** Chosen.

## Decisions

- New GA date 2026-09-15, on the regular release train.
- SSO on the train of 2026-06-30, enabled only for Meridale's organization at first.
- Waitlist beta extended to 2026-08-21.
- Customer communication: Felix drafts, Imani's team sends to all accounts by 2026-06-05. No new date given to customers beyond "September" until 2026-08.
- Lucia to take over the release train from July. This had been under discussion with my coach since April; the meeting made the timing obvious.

## What I take from it

The slip was not an estimation failure on the features. It was a capacity failure I could have seen in March: we kept the June date while two engineers were on platform work that had no end date. More in [[lessons-from-the-version-3-slip]] and the stance in [[dates-are-promises-only-when-contractual]].

## Follow-up

- 2026-06-30: SSO live, see [[sso-go-live-2026-06-30]].
- 2026-09-15: GA, see [[version-3-general-availability-2026-09-15]].
