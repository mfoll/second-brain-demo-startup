---
type: Question
status: Deferred
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reminder-pipeline-overview]]"
  - "[[platform-engineering]]"
_organized: true
---

# Should We Move The Job Queue Off Redis?

Raised by [[hamish-pettigrew]] in 2026-04: our Redis-backed queue loses jobs on a failover unless persistence is tuned, and it carries every reminder.

## Options

1. Keep Redis, enable append-only persistence and test failover.
2. A PostgreSQL-backed queue (one less system; more load on the primary).
3. A managed queue service (new vendor, new SOC 2 vendor review).

## Status

Deferred on 2026-05-11 after option 1 was done and a failover test lost no jobs. Revisit if the queue causes an incident or if a platform engineer is hired.
