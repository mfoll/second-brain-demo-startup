---
type: Question
status: Answered
belongs_to: "[[waitlist-autofill]]"
related_to:
  - "[[appointment-slot-model]]"
  - "[[felix-ostrowski]]"
  - "[[hamish-pettigrew]]"
_organized: true
---

# How Should The Waitlist Pick The Next Patient?

## Question

When a slot frees up, which person on the clinic's waitlist gets the offer first?

## Current Answer

> [!info]
> First-come among the people whose stated availability fits the slot (day, time window, site, staff preference), with a manual priority flag that front-desk staff can set. Nothing clinical is ever used to rank.

Decided 2026-02-18 by Felix, Hamish and me; confirmed by the beta.

## Options considered

1. **Strict first-come.** Hamish's first proposal. Simple to explain, but in tests 40% of offers went to people who had said they could not come at that time, and each refusal burned 30 minutes of the slot.
2. **Best fit by preferences.** Felix's proposal: score each candidate by how well the slot matches their preferred times. Rejected because front-desk staff could not explain to a caller why someone who joined later got the slot first.
3. **First-come among fitting candidates, plus a manual flag.** Chosen.

## Evidence

- Beta acceptance within the 30-minute hold was 61% ([[waitlist-autofill-beta-metrics]]), against an estimated 35% for strict first-come in the February simulation.
- The manual flag was used on 4% of entries in the beta, mostly for people who had been bumped before.

## Remaining edge

Whether to offer to two people at once for hard-to-fill slots. Not now; it complicates the hold and front desks did not ask for it.
