---
type: Concept
maturity: Seed
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[wikipedia-service-level-objective]]"
  - "[[what-is-our-reminder-delivery-target]]"
  - "[[wikipedia-site-reliability-engineering]]"
_organized: true
---

# Error Budget

The amount of unreliability a service-level objective allows over a period. If the target is 99.5% of reminders sent within 15 minutes of schedule, the budget is the other 0.5%. While budget remains, the team ships; when it is spent, reliability work comes first. The idea comes from [[wikipedia-site-reliability-engineering]] practice and builds on [[wikipedia-service-level-objective]].

## Our Use So Far

Only for reminders, and only informally. Reminders are about 800,000 a month, so a 0.5% budget is about 4,000 late or missed reminders a month. The March outage alone spent 4,212, more than a month's budget in one day.

## Why Not More

Seven engineers and one on-call rotation do not need a formal policy yet. What I want from the idea is a shared number to argue with when Felix and Kwabena disagree about roadmap versus reliability. See [[what-is-our-reminder-delivery-target]].
