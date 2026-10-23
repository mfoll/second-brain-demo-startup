---
type: Source
source_type: Documentation
publisher: Amazon Web Services
url: https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html
date_accessed: 2026-10-23
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[should-meridale-get-a-customer-managed-encryption-key]]"
  - "[[enterprise-dedicated-databases]]"
_organized: true
---

# Encrypting Amazon RDS Resources

Amazon RDS User Guide page on encryption at rest for DB instances.

## Summary

- RDS encryption covers the instance storage, logs, automated backups, read replicas and snapshots, using AES-256, transparently to clients.
- Keys come from AWS KMS: the AWS managed key for RDS, or a customer managed key whose policy you control; KMS key use can be audited through CloudTrail.
- The KMS key of an encrypted instance cannot be changed after creation; changing it means copying a snapshot with a new key and restoring, or a blue/green deployment.
- Encryption can only be enabled at creation. An unencrypted instance can be encrypted only via an encrypted snapshot copy and restore.
- If the KMS key is disabled, RDS loses access and the instance moves to an inaccessible state, recoverable for seven days.

## Why It Matters

It is the basis for our answer to Meridale on encryption keys ([[should-meridale-get-a-customer-managed-encryption-key]]): a customer managed key per enterprise database, chosen at creation, held in our account. The disabled-key behavior is why we declined a key held in the customer's own account.

## Source Links

- [Encrypting Amazon RDS resources](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.Encryption.html)
