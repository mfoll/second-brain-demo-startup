---
type: Question
status: Deferred
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reminder-pipeline-overview]]"
  - "[[bettina-solberg]]"
_organized: true
---

# Should Reminders Fall Back To Email When SMS Is Throttled?

On 2026-03-17 email reminders kept working while SMS was throttled. Should the pipeline switch a reminder to email when SMS cannot go out in time?

## Considerations

- Only about 40% of patient contacts have an email address on file.
- Clinics chose SMS for a reason; a changed channel without notice may confuse patients and front desks.
- Pingrove's second sender account (quote in [[pingrove-retry-correspondence]]) solves throughput, not a Pingrove outage.

## Status

Deferred on 2026-05-06: the token bucket and backoff removed the immediate risk. Revisit if Pingrove has an outage of its own or if the [[pingrove-api-documentation]] limits change at the 2027-02 renewal.
