---
type: Question
status: Open
belongs_to: "[[platform-engineer-hire]]"
related_to:
  - "[[engineering-budget-2027]]"
  - "[[kwabena-asare]]"
  - "[[felix-ostrowski]]"
  - "[[platform-engineering]]"
_organized: true
---

# Should We Hire A Platform Engineer Or Keep Everyone On Call?

The seed extension funds two engineering hires in 2027. Should the first one be a dedicated platform engineer, so that on-call and infrastructure stop eating product time, or a second product engineer for the 2027 roadmap, with everyone staying in the rotation?

## Current Answer

> [!question]
> Not decided as of 2026-10-23. I will decide after the 2026-Q4 paging data (pulled 2026-11-30) and the draft 2027 roadmap, and present the choice at the 2026-12-08 board meeting together with the [[engineering-budget-2027]].

## The two cases

**Kwabena's case** ([[kwabena-platform-hire-memo]], 2026-10-12). Pages averaged 9 a week in 2026-Q3, 38 of 117 out of hours. Most come from three sources: reminder queue age, database connections and Pingrove delivery errors. Each needs sustained work that nobody has time for between rotations: connection pooling tuning, queue partitioning, the paused [[observability-overhaul]]. A platform engineer would own Terraform, the database and alerting, and take primary during working hours, so product engineers could move to a secondary-only rotation. He also points to the bus factor: today he and Bram are the only people comfortable in `quaylane-infra`.

**Felix's case** ([[felix-product-engineer-memo]], 2026-10-15). The 2027 roadmap draft has the [[online-booking-widget]], reporting for clinic groups and the Meridale follow-ons. With seven engineers and the 2026 feature velocity, he estimates we can deliver about 60% of it. A product engineer pays back in roadmap items that customers have asked for, and paging volume should fall anyway as the post-outage fixes settle.

## Evidence so far

- [[paging-report-2026-q3]]: 117 pages in 13 weeks; 31 reminder queue age, 19 database connections, 17 Pingrove delivery errors, the rest spread out.
- Q2 was 132 pages in the 10 weeks after the rotation started, so the trend is down but not fast.
- [[team-health-survey-2026-06]]: on-call sustainability 3.5 of 5, up from 2.6.
- [[platform-engineer-conversation-2026-10-07]] and [[founders-circle-2026-09-10]]: two outside views, both suggesting a first platform hire somewhere between 15 and 25 people.

## What would decide it

- If Q4 pages stay above about 8 a week, or out-of-hours pages above 3 a week, I lean platform first.
- If the roadmap review shows a contractual commitment (Meridale or another enterprise deal) that needs product capacity in 2027-H1, I lean product first.
- What I will not do is hire a platform engineer to make on-call someone else's problem. Everyone keeps a secondary week either way.

## Related

- [[how-many-pages-a-week-is-too-many]]
- [[alert-fatigue]]
- [[platform-engineer-role-draft]]
