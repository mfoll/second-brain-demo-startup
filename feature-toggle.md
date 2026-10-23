---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Feature_toggle
date_accessed: 2026-10-23
last_edited: 2026-10-18
licence: CC BY-SA 4.0
belongs_to: "[[version-3-release]]"
related_to:
  - "[[feature-flag-inventory-v3]]"
  - "[[cut-a-release]]"
_organized: true
---

# Feature toggle

Wikipedia article, last edited 2026-10-18.

## Summary

Explains feature toggles: runtime conditions that switch a feature on or off, used as an alternative to long-lived feature branches. They let teams release often, enable a feature for some users before all, and run canary releases or experiments.

## Why It Matters

Quaylane 3.0 shipped six flags, and the 2.x years left us nine flags nobody could explain. Lucia used this article in the engineering meeting of 2026-07-15 to argue that flags are a release tool with a lifetime, not configuration. The result is the rule in [[feature-flag-inventory-v3]]: every flag has an owner and a removal date, checked at each [[cut-a-release]] train.

## Caveats

The article treats flags broadly; it does not tell you when to remove them, which is the hard part.

## Source Links

- [Feature toggle](https://en.wikipedia.org/wiki/Feature_toggle), CC BY-SA 4.0
