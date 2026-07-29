# AgriGrow Farmer Dashboard — System Requirements Specification

**Document ID:** AgriGrow-FARM-SRS-007 | **Version:** 1.0

The web dashboard complements—not replaces—the mobile experience for family members, FPO staff and advisors assisting a farmer. It is responsive, low-bandwidth and available in the same language model as the app.

## Capabilities

| Area | Requirement |
|---|---|
| Farm home | Show farms, fields, active crop cycles, last-sync status and only the most actionable current alerts. |
| Field timeline | Plot measured values by method and depth, calibrated/estimated badges, lab results, advisories and farmer actions. Never blend incompatible methods into one line. |
| Map | Show consent-authorised boundaries/sampling points and location-accuracy circle; allow landmark-only fields. |
| Recommendations | Present priority, expected benefit/risk, evidence, assumptions, expiry, cost/effort band and escalation option. |
| Device care | Calibration schedule, probe replacement, battery health and synchronisation diagnostics without exposing security secrets. |
| Records | Export own authorised data in documented CSV/JSON, correct context through linked events, and manage sharing/consent. |

## Roles and privacy

Farmer owner may view/export own data and nominate a delegate. FPO operator sees only explicit member grants; agronomist sees assigned farms and cannot re-share raw data; support sees pseudonymised diagnostics by default. All downloads, delegate changes, advisory overrides and exports appear in an activity log. Dashboard pages call purpose-scoped APIs; front-end hiding is never the access control.

## Usability and acceptance

The default home page must answer: “What needs my attention?”, “What did I measure?”, and “Can I trust it?” in one screen. Support Chrome/Android baseline and common low-bandwidth browsers; avoid mandatory maps/video. Test with farmers and delegates in target languages, keyboard-only navigation, screen reader, 200% zoom and 2G-throttled performance. Any comparison chart displays unit, method, depth and quality legend.
