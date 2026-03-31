---
type: Concept
maturity: Evergreen
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[scim-protocol-rfc-7644]]"
  - "[[security-and-privacy]]"
_organized: true
---

# SCIM Deprovisioning

Removing a user's access in Quaylane automatically when the customer disables them in their own identity provider, using SCIM. It is the part of SSO that matters most for security and for SOC 2 offboarding evidence.

## How it works for us

- The customer's identity provider calls our SCIM endpoint for `/Users`. A `PATCH` setting `active` to false, or a `DELETE`, ends every session for that user and blocks new logins.
- We keep the user row for audit history and anonymize the display name after 90 days.
- Every deprovisioning writes an audit event with the IdP's request ID.

## Why it matters

Without SCIM, a front-desk employee who leaves a Meridale clinic keeps Quaylane access until someone remembers to remove them. With SSO alone they cannot log in, but existing sessions live on. Meridale's questionnaire asked about exactly this.

## Measured

About two minutes from disable to access removed in the go-live test ([[scim-deprovisioning-test-log]]).

Protocol reference: [[scim-protocol-rfc-7644]]. Background: [[system-for-cross-domain-identity-management]].
