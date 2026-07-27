---
type: Source
source_type: Internal document
date_accessed: 2026-07-02
belongs_to: "[[enterprise-dedicated-databases]]"
related_to:
  - "[[meridale-clinic-group]]"
  - "[[samir-haddad]]"
_organized: true
---

# Meridale Dedicated Database Design Doc

Two-page design for Meridale's dedicated database, written by [[teodora-vasilescu]] and [[kwabena-asare]] on 2026-06-24 and shared with [[samir-haddad]] on 2026-07-02.

## Summary

Separate RDS instance, own KMS key, separate backups, migration lane after the shared database, RLS policies applied as a second layer, shared application tier. Lists what is not separate: the API and workers, the job queue, the email and SMS providers.

## Why It Matters

Samir accepted it on 2026-07-08 with one request: the KMS key policy excerpt, which we shared redacted. It is the document to reuse for the next enterprise questionnaire.

## Source Location

Engineering shared drive, `Tenant isolation/meridale-dedicated-db`; the version sent is in the Meridale account folder.
