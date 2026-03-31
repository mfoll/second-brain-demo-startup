---
type: Concept
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[code-review-and-delivery]]"
  - "[[ship-an-emergency-change]]"
_organized: true
---

# Break-Glass Change

A change that is allowed to skip a normal control because waiting would cause more harm, on condition that the skip is visible and the control is applied afterwards. The name comes from the emergency key behind glass: anyone may break it, and everyone can see that it was broken.

## How it works for us

Our control is one recorded approval before merge ([[code-review-policy]]). The break-glass version keeps the control's intent with three conditions: a small named group can perform the bypass, every bypass is logged ([[break-glass-change-log]]), and a second engineer reviews it within one business day. The procedure is [[ship-an-emergency-change]].

## What makes it work

- It has to be rare enough that each use is discussed. Five uses in six months is about right; fifty would mean the control is wrong.
- The audit trail has to be automatic where possible. GitHub records bypass merges; [[olu-ajayi|Olu]]'s watcher checks the log against them.
- The review afterwards is a real review, not a signature. Two of the five post-merge reviews led to follow-up fixes.

## Where else it applies

Production database access during an incident, and emergency access to the AWS account, both handled by [[kwabena-asare]] under [[run-the-platform]] on the same pattern.
