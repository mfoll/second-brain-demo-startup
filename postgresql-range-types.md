---
type: Source
source_type: Documentation
publisher: The PostgreSQL Global Development Group
url: https://www.postgresql.org/docs/16/rangetypes.html
date_accessed: 2026-10-22
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[appointment-slot-model]]"
  - "[[scheduling-engine-overview]]"
_organized: true
---

# PostgreSQL 16 Documentation: 8.17. Range Types

## Summary

The section of the PostgreSQL 16 manual on range types: values that represent a range of some ordered subtype, such as timestamps. `tstzrange` is the built-in range over `timestamp with time zone`. The manual recommends exclusion constraints rather than unique constraints for ranges, and shows an `EXCLUDE USING GIST` constraint with the overlap operator that rejects a new row whose range overlaps an existing one. With the `btree_gist` extension, the constraint can combine equality on another column (a room, in its example) with overlap on the range, so only overlaps for the same room are rejected.

## Why It Matters

This is the mechanism behind the core invariant of the [[appointment-slot-model]]: no two appointments or holds overlap on the same room or staff member. Nadia Carvalho chose it in 2023; Teodora cited this page in the 2026 rewrite of the [[scheduling-engine-overview]] when Arun Velayudhan asked how double-bookings are prevented under concurrency.

## Key Details

- Range types need a subtype with a total order.
- Exclusion constraints on ranges use a GiST index.
- The per-resource version needs `btree_gist` for the equality part.

## Caveats

The manual's examples use `tsrange`; we use `tstzrange`. The behavior of the constraint is the same.

## Source Links

- [PostgreSQL 16: Range Types](https://www.postgresql.org/docs/16/rangetypes.html)
