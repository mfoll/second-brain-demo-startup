---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Separation_of_duties
licence: CC BY-SA 4.0
date_accessed: 2026-10-23
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[code-review-policy]]"
_organized: true
---

# Separation Of Duties

English Wikipedia article, last edited 2026-10-06.

## Summary

Separation (or segregation) of duties is the practice of requiring more than one person to complete a task, used as an administrative control against fraud, sabotage, theft, misuse of information and other security breaches.

## Why It Matters

It is the principle behind the change management control CM-01 in the [[soc2-control-matrix]]: the person who writes a change is not the only person who approves it for production. That is why [[patrice-ndour]] wanted a recorded approval by someone other than the author, and why the break-glass path in [[ship-an-emergency-change]] still requires a second engineer's review within one business day. It also explains, I think, why pair-programmed commits were not enough for him: two people may have worked on the change, but the record shows one author approving their own merge.

## Caveats

General principle; how far to apply it in a team of eight is a judgment call, and the article does not settle the pairing debate.

## Source Links

- [Separation of duties](https://en.wikipedia.org/wiki/Separation_of_duties), CC BY-SA 4.0.
