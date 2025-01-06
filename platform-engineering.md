---
type: Topic
belongs_to: "[[exploratory-reading]]"
related_to:
  - "[[run-the-platform]]"
  - "[[platform-engineer-hire]]"
_organized: true
---

# Platform Engineering

Exploration cluster: reading and notes on whether a company of our size should have anyone whose job is the internal platform rather than the product. No project owns this yet; if we decide on a platform hire at the 2026-12-08 board meeting, this cluster moves under [[platform-engineer-hire]].

## Why I Am Reading This

Since the on-call redesign six engineers share the rotation and Kwabena carries most infrastructure work by default. Pages averaged 9 a week in 2026-Q3. [[bram-verhoef]] joined in July as an engineer focused on the platform, but he is also on product tickets half the time. The question I keep circling is in [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]].

## Notes So Far

- [[wikipedia-site-reliability-engineering]] gives some of the vocabulary. Most writing on platform teams assumes dozens of product teams; we have one.
- [[wikipedia-infrastructure-as-code]]: our `quaylane-infra` repository already does most of what a small platform team would own. See [[infrastructure-map]].
- A conversation with [[sigrid-aaltonen]]: she hired her first platform person at around 25 engineers and thinks earlier is a luxury.
- [[rohan-deshpande]], a platform engineer I spoke to in 2026-10, described the job at his company as mostly paved paths for deploys and databases.
- Opinion forming, not yet written: a platform role at our size is only worth it if it removes paging from product engineers, not if it builds tooling nobody asked for.

## Open Threads

- [[should-we-move-the-job-queue-off-redis]] would be platform work either way.
- [[rds-capacity-plan-2027]] gives the infrastructure workload the role would inherit.
