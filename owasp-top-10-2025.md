---
type: Source
source_type: Documentation
publisher: OWASP Foundation
url: https://top10.owasp.org/2025/
date_accessed: 2026-10-23
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[bracken-hollow-pen-test-report-2026]]"
  - "[[owasp-application-security-verification-standard]]"
_organized: true
---

# OWASP Top 10:2025

The 2025 edition of the OWASP Top 10 list of web application security risk categories.

## The Ten Categories

A01 Broken Access Control; A02 Security Misconfiguration; A03 Software Supply Chain Failures; A04 Cryptographic Failures; A05 Injection; A06 Insecure Design; A07 Authentication Failures; A08 Software or Data Integrity Failures; A09 Security Logging and Alerting Failures; A10 Mishandling of Exceptional Conditions.

## Why It Matters

- A01 is where tenant isolation sits for a multi-tenant app; it is the first thing [[ivo-radic]] tested ([[bracken-hollow-pen-test-report-2026]]).
- A10 covers the kind of verbose error messages that were our one medium pen test finding.
- A03 is a reminder that dependency scanning (control VM-01) matters as much as our own code.
- A09 connects to the queue-age alert work after the March outage, under [[run-the-platform]].

We use the list as a shared vocabulary in security reviews of pull requests, not as a checklist.

## Source Links

- [OWASP Top 10:2025](https://top10.owasp.org/2025/)
