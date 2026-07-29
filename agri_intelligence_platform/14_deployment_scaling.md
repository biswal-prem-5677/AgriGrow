# AgriGrow Deployment and Scaling Plan

**Document ID:** AgriGrow-DEP-014 | **Version:** 1.0

## 1. Deployment sequence

| Phase | Scale | Objective | Exit condition |
|---|---:|---|---|
| Discovery | 30–60 users | Validate workflows, language, measurement protocols and service model | Protocol usable; no unresolved safety blocker |
| Pilot | 300–1,000 devices | Validate three agro-climatic zones, repair/sync/quality operations | Reference comparison and support targets met |
| Regional rollout | 10k–50k | Prove manufacturing, FPO training and cloud operations | PVT yield, cohort retention and DR evidence met |
| National programmes | staged | Scale with tenant/data-sharing agreements and regional adaptation | Capacity, governance and support readiness independently approved |

Do not use device shipment as deployment success. An activated device must have trained user/operator, assigned service route, calibrated probe, consent status, known connectivity pathway and support channel.

## 2. Operations model

Provision devices against a work order, verify factory test record, ship in tamper-evident packaging, activate only at controlled handover, and register calibration/ownership. Extension partners train with a standard sample protocol and assessment; service partners stock probes, batteries and port/gasket kits. Every district has escalation path for hardware, measurement, app/account, advisory and privacy issues.

Cloud deploys by environment and region with infrastructure-as-code, canary/rollback, dashboard SLOs and capacity load tests. Backfill/replay uses isolated pipelines and immutable event IDs. Regional data residency, government programme tenancy and cross-border processing are decisions made by legal/security architecture—not inferred from a cloud-provider region label.

## 3. Scaling risks and controls

| Risk | Control |
|---|---|
| Connectivity gaps | Offline queue, phone gateway, FPO sync points, delayed-notification expectations |
| Calibration burden | Consumable plan, reminders, field reference kits, quality-based advisory gating |
| Biased coverage | Publish coverage/method quality; targeted sampling rather than extrapolation |
| Support overload | Tiered support, diagnostic bundles, swap/repair SLA, training certification |
| Cloud reconnect storm | Partitioning, backoff/jitter, queue quotas and synthetic outage drills |
| Premature national claims | Independent pilot evidence and phased regional approval |

## 4. Observability and SLOs

Track activation-to-first-valid-measurement, calibration freshness, sync latency/backlog, OTA success/rollback, crash rate, advisory availability/override, repair turnaround, data-quality distribution and privacy/security events. Publish operational status and customer-impact communication. Test DR at least twice yearly: restore a clean environment, replay a representative event set, validate authorisation/audit integrity and document actual RTO/RPO.
