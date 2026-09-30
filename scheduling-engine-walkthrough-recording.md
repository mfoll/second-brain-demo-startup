---
type: Source
source_type: Internal recording
date_accessed: 2026-09-09
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[what-should-the-scheduling-engine-bus-factor-be]]"
  - "[[teodora-vasilescu]]"
  - "[[bus-factor]]"
_organized: true
---

# Scheduling Engine Walkthrough Recording

Recorded walkthrough of the scheduling engine by [[teodora-vasilescu]] on 2026-09-09, 2 h 10 min in four parts, one of the follow-ups from the [[technical-diligence-call-2026-08-19]].

## Contents

- How a slot request becomes a constraint set: rooms, staff rosters, equipment, clinic rules.
- The solver loop and why it is greedy rather than exhaustive.
- Multi-site handling added for [[multi-location-calendars]].
- Known sharp edges: time zone changes, recurring appointments across roster changes.
- How to run the engine's property tests locally.

## Use

Part of week 2 in the [[onboarding-plan-for-new-engineers]] since 2026-09, and the starting point for each engineer on the [[pairing-rotation-scheduling-engine]].

## Source Location

Engineering video library, `Architecture / scheduling-engine-2026-09`, with slides in the same folder. Contains no customer data; examples use a synthetic tenant.
