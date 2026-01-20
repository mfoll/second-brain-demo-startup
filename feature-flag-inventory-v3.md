---
type: Note
belongs_to: "[[version-3-release]]"
related_to:
  - "[[feature-toggle]]"
  - "[[lucia-ferreyra]]"
_organized: true
---

# Feature Flag Inventory V3

The feature flags created for Quaylane 3.0 and their removal plan. Flags are cheap to add and expensive to forget; after 2.x we found nine flags nobody could explain.

| Flag | Purpose | Default after GA | Owner | Remove by |
| --- | --- | --- | --- | --- |
| `waitlist_autofill` | Per-account switch for waitlist offers | Off, account setting | Hamish | Keep as setting; flag code removed 2026-11-30 |
| `multi_site_view` | Cross-site calendar | On for multi-site accounts | Lucia | 2026-11-30 |
| `site_move_flow` | Moving appointments between sites | On | Lucia | 2026-11-30 |
| `saml_sso` | Per-organization SAML login | On for enterprise plans | Min-jae | Keep as setting |
| `scim_endpoint` | SCIM provisioning | On for SSO organizations | Min-jae | 2026-11-30 |
| `calendar_windowed_render` | July performance work | On | Lucia | Removed 2026-10-06 |

## Rule since 3.0

Every flag gets an owner and a removal date when it is created, recorded in the pull request. Lucia checks the list at each release train. General background on the pattern: [[feature-toggle]].
