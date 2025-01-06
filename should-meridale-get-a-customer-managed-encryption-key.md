---
type: Question
status: Answered
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[enterprise-dedicated-databases]]"
  - "[[amazon-rds-encryption-at-rest]]"
  - "[[samir-haddad]]"
_organized: true
---

# Should Meridale Get A Customer-Managed Encryption Key?

Question 68 of the [[meridale-security-questionnaire]] asked whether Meridale's data could be encrypted with a key specific to Meridale. The contract then required a dedicated database.

## Answer

Yes, as part of the dedicated database, answered 2026-06-25 and live 2026-08-21. Meridale's database is a separate RDS instance encrypted with its own AWS KMS customer managed key in our account, not a key Meridale holds. That gives a separate key per enterprise tenant and a CloudTrail record of key use, which is what [[samir-haddad]] wanted.

## Why Not a Key Meridale Controls

A key held in the customer's account would let Meridale make its own database unreadable by disabling the key, and RDS would stop the instance. We would carry the availability risk for a step outside our control. Samir accepted our-account keys with key usage logs on request.

## Constraint Worth Remembering

RDS cannot change the KMS key of an existing encrypted instance; a key change means a snapshot copy and restore ([[amazon-rds-encryption-at-rest]]). Choose the key at creation, which the [[enterprise-dedicated-databases]] runbook now does.
