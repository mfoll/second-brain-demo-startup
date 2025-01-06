---
type: Concept
_organized: true
---

# Toil

Manual, repetitive operational work that scales with the size of the service and leaves nothing lasting behind: restarting a stuck worker by hand, exporting the same access lists every quarter, re-running a failed import because nobody automated the retry.

## How I use it

The word helps separate two kinds of on-call load. Pages that need judgment are the job of whoever is on call. Pages and chores that need only a runbook are toil, and toil is a signal to automate rather than a reason to add people.

In our case the quarterly access review took most of an afternoon producing exports, and several reminder pages in Q3 ended with the same manual requeue. Both are toil by this definition.

## Caveat

Not all repetitive work is toil. Reviewing a pull request repeats too, and it is the point of the job.
