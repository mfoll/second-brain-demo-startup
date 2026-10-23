---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Principle_of_least_privilege
licence: CC BY-SA 4.0
date_accessed: 2026-10-23
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[run-the-quarterly-access-review]]"
  - "[[information-security-policy]]"
_organized: true
---

# Principle Of Least Privilege

English Wikipedia article, last edited 2026-10-06.

## Summary

The principle of least privilege says that every module, user or program in a system should be able to access only the information and resources it needs for its legitimate purpose.

## Why It Matters

It is the rule behind control AC-06 in the [[soc2-control-matrix]] and the question each reviewer asks in [[run-the-quarterly-access-review]]: does this person or service account need this access to do its job today? In the 2026-10-06 review it removed one service account with RDS write access that nothing used, and moved two engineers' standing production read access into the on-call break-glass role ([[quarterly-access-review-2026-10-06]]). It also applies inside the database: the application role must not be a role that bypasses [[row-level-security]].

## Caveats

A principle, not a procedure; the hard part is deciding what "needs" means for an on-call engineer at 3 a.m.

## Source Links

- [Principle of least privilege](https://en.wikipedia.org/wiki/Principle_of_least_privilege), CC BY-SA 4.0.
