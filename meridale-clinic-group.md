---
type: Source
source_type: Internal account record
date_accessed: 2026-10-21
belongs_to: "[[meridale-enterprise-rollout]]"
related_to:
  - "[[victoria-ashdown]]"
  - "[[meridale-commitments-tracker]]"
  - "[[meridale-security-questionnaire]]"
_organized: true
---

# Meridale Clinic Group

Account record for Meridale Clinic Group, our largest customer: 42 outpatient clinics on a three-year contract signed 2026-01-12 at $186,000 a year. This note is the engineering view of the account. The signed contract and pricing schedule stay in the sales folder and the CRM; this note points there.

## Summary

- Group of 42 outpatient clinics (physiotherapy, imaging and general outpatient services) under one operations team.
- Pilot: 3 clinics from 2025-06-02.
- Contract: signed 2026-01-12, three years, $186,000 a year, about 17% of ARR. Closed by [[dana-prescott|Dana Prescott]] with [[renata-castellano|Renata]].
- Three engineering conditions, all met: SSO by 2026-07-01 (live 2026-06-30), a dedicated database (live 2026-08-21), a SOC 2 Type I report by 2026-09-30 (issued 2026-08-28).
- Rollout: 19 of 42 clinics live on 2026-10-23, target all 42 by 2026-12-11.

## Why It Matters

Meridale changed the company. Their [[meridale-security-questionnaire]] (186 questions, received 2025-09-15) triggered the [[architecture-review-2025-11-18]] and the whole [[tenant-isolation-migration]]. Their SSO date shaped the [[version-3-release]] and forced the split at [[release-planning-2026-06-02]]. Their SOC 2 condition set the deadline for the [[soc2-type-1-audit]]. The partial reversal of the tenant decision at [[architecture-review-2026-06-11]] kept their dedicated database because the contract requires it.

It also carries concentration risk. Copperwell asked about it during the [[technical-diligence-call-2026-08-19]]: one account at 17% of revenue, with commitments that drove most of our 2026 architecture.

## Key Details

### Contract conditions

| Condition | Contract date | Delivered | Evidence |
| --- | --- | --- | --- |
| SAML SSO with deprovisioning | 2026-07-01 | 2026-06-30 | [[sso-go-live-2026-06-30]] |
| Dedicated database for Meridale data | before first wave | 2026-08-21 | [[enterprise-dedicated-databases]] |
| SOC 2 Type I report | 2026-09-30 | 2026-08-28 | [[soc2-type-1-report]] |

The SOC 2 report carried two exceptions (quarterly access review not yet evidenced; one leaver's laptop returned without a wipe record). Samir Haddad accepted the report with a request to see both closed in the Type II period; see [[soc2-type-2-observation]].

Other commitments: 99.5% monthly availability for the scheduling app (met every month since signing, including March, because the outage hit reminders rather than the app), a named engineering contact per wave, and 30 days' notice of breaking changes to the CSV export.

### Contacts

- [[victoria-ashdown|Victoria Ashdown]], COO, executive sponsor.
- [[samir-haddad|Samir Haddad]], IT and security manager; identity provider and security reviews.
- [[rania-saleh|Rania Saleh]], procurement; contract amendments and invoices.
- [[joanne-pruett|Joanne Pruett]], front-desk operations lead at a pilot clinic; training.

### Rollout status

| Wave | Date | Clinics | Cumulative |
| --- | --- | --- | --- |
| Pilot | 2025-06-02 | 3 | 3 |
| Wave 1 | 2026-09-08 | 8 | 11 |
| Wave 2 | 2026-10-06 | 8 | 19 |
| Wave 3 | 2026-11-03 (planned) | 12 | 31 |
| Wave 4 | 2026-12-01 (planned) | 11 | 42 |

Detail per clinic in [[meridale-rollout-tracker]].

### Data

Meridale's tenant is `tenant 2044` in the dedicated cluster since 2026-08-21. They are the only tenant with their own encryption key and migration lane.

## Caveats

- Revenue share is computed against ARR of about $1.1M in 2026-10 and will drop as other accounts grow.
- The availability commitment covers the web app only. Reminder delivery is best effort in the contract, which we should not rely on after March.

## Source Location

- Signed contract and order form: sales folder in Google Drive, `Customers/Meridale/Contract/`, owned by Dana Prescott. Read access for founders only.
- CRM account record: owned by Dana.
- Contract summary for engineering: [[meridale-master-services-agreement]].
