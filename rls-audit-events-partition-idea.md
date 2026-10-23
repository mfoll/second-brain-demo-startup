---
type: Note
date: 2026-10-20
related_to: "[[row-level-security-rollout]]"
_organized: false
---

# RLS on audit_events, partition idea

Bram in our 1:1: `audit_events` is partitioned by month, so policies have to exist on every partition, and new partitions are created by the cron job. If the job forgets, the new partition has no policy and nobody notices until the coverage check.

His idea: attach the policy in the partition creation function itself + add a CI check that fails if any partition of a tenant-scoped table lacks `FORCE ROW LEVEL SECURITY`. Teodora to review.

Q for me: does the coverage tracker count partitions as separate tables? If yes 41/47 is wrong-ish. ask Kwabena.
