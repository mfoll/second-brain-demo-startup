---
type: Question
status: Open
belongs_to: "[[engineering-metrics]]"
related_to:
  - "[[dora-four-keys]]"
  - "[[margot-ellison]]"
  - "[[engineering-budget-2027]]"
_organized: true
---

# Which Engineering Metrics Should We Show The Board?

[[margot-ellison|Margot Ellison]] asked in September for "a few engineering numbers each quarter" from the 2026-12-08 meeting on. Which ones help the board judge engineering without turning into targets?

## Candidates

- Deployment frequency and change failure rate from the [[dora-four-keys]] log: about 11 deploys a week in Q3, change failure rate about 6%.
- Pages per week and out-of-hours pages ([[paging-report-2026-q3]]). Directly tied to the 2027 hire.
- Uptime of the reminder pipeline against the internal target. Ties to the outage the board already knows about.
- Cloud cost per clinic, $14 a month, which Copperwell already asked about in diligence.

## Not these

- Anything per engineer. Velocity points, pull requests per person, lines of code. [[goodharts-law]].
- Time to first review: useful for us, meaningless to the board.

## Leaning

Three numbers: deploys a week, pages a week, cost per clinic, each with a one-line comment. Decide by 2026-11-27 so Renata can put them in the deck.
