---
type: Question
status: Open
belongs_to: "[[online-booking-widget]]"
related_to:
  - "[[roadmap-2027]]"
  - "[[booking-widget-is-a-different-product]]"
  - "[[booking-widget-estimate]]"
_organized: true
---

# Should The Booking Widget Ship In 2027?

## Question

Do we build patient self-booking from clinic websites in 2027, given its pull in the feedback log and its cost in engineering, security and focus?

## Current State

Open. Decision expected at the leadership meeting of 2026-11-17 and confirmed with the roadmap on 2026-12-08.

## Case for

- 212 feedback items since 2025-03 across 71 accounts in 2026 alone ([[customer-feedback-log]]).
- Named in four of 23 churn reasons in 2025 ([[churn-analysis-2025]]).
- Interviews show practice managers would pay for it ([[booking-widget-discovery-interviews]]).

## Case against

- 14 to 20 engineer-weeks plus about 3 weeks of security work for a minimal version ([[booking-widget-estimate]]), about a third of the 2027 roadmap capacity if the hire goes to platform.
- A new public, unauthenticated surface with new abuse cases and a change to the SOC 2 scope during the Type II observation.
- Front-desk leads such as Joanne Pruett want strict controls on what is bookable, which makes the minimal version less minimal.

## What would settle it

- The estimate review by Teodora and Lucia.
- Whether the first 2027 hire is a product engineer ([[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]).
- A rough price for a pre-launch penetration test.

My current lean is in [[booking-widget-is-a-different-product]].
