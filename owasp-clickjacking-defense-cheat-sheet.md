---
type: Source
source_type: Documentation
publisher: OWASP Foundation
url: https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html
date_accessed: 2026-10-22
belongs_to: "[[online-booking-widget]]"
related_to:
  - "[[booking-widget-estimate]]"
  - "[[security-and-privacy]]"
_organized: true
---

# Clickjacking Defense Cheat Sheet

OWASP Cheat Sheet Series.

## Summary

Defenses against pages being framed by hostile sites. The preferred control is the Content Security Policy `frame-ancestors` directive sent as an HTTP header, set to `'none'` unless framing is needed, and otherwise listing the allowed origins explicitly. `X-Frame-Options` with `DENY` or `SAMEORIGIN` is the older control; its `ALLOW-FROM` option is obsolete and can name only one origin. `SameSite` cookies help where an attack depends on the user's session but do not stop framing.

## Why It Matters

The [[online-booking-widget]] would be embedded on clinics' own websites, which is exactly the case where framing must be allowed for some origins and refused for all others. The cheat sheet shaped the security line of the [[booking-widget-estimate]]: a per-clinic list of allowed origins served as `frame-ancestors`, which `X-Frame-Options` cannot express. Today the web app sends `frame-ancestors 'none'`.

## Key Details

- Wildcard subdomains do not cover the bare domain; list both.
- Headers, not meta tags.

## Caveats

Framing control is one part of the widget's security; bot bookings and rate limits are separate problems.

## Source Links

- [Clickjacking Defense Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Clickjacking_Defense_Cheat_Sheet.html)
