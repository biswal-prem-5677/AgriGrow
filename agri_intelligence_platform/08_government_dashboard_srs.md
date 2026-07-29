# AgriGrow Government Dashboard — System Requirements Specification

**Document ID:** AgriGrow-GOV-SRS-008 | **Version:** 1.0

## 1. Purpose and guardrails

This dashboard supports programme monitoring, extension planning and authorised disaster/agronomy intelligence. It is not a surveillance tool, a farmer-ranking system, or an eligibility engine. Individual records are inaccessible unless a separately documented legal mandate, purpose, role and consent/authority pathway permits it.

## 2. Views and controls

| View | Function | Mandatory control |
|---|---|---|
| Coverage | Active devices, measurement completeness, calibration freshness by district/block/crop | Suppress cells below k-anonymity threshold; show sampling bias warning. |
| Agro indicators | Quality-filtered pH/EC/moisture/rain-risk trends | Show method mix, sample count, confidence and data vintage. |
| Programme operations | Campaign progress, training/support needs, device health | Organisation/role scoping and audit log. |
| Alerts | Configured threshold alerts for regional conditions | Human review, source provenance, no automatic farmer action. |
| Exports | Approved aggregate or research release packages | Data steward approval, purpose, retention and watermark. |

Default geography is coarse enough to avoid re-identification. Map tiles use aggregation and jitter/suppression rules approved by privacy review. Analysts cannot join location, identity and sensitive attributes through the UI or export endpoint. Every query carries a purpose code, role, time and policy decision; anomaly detection flags bulk/rare queries.

## 3. Data integrity and interpretation

Show measurement coverage separately from farm population so a highly instrumented district is not mistaken for a representative district. Every chart exposes data source, time window, eligible quality states, calculation definition, confidence and last refresh. A government user can annotate an intervention but may not change raw sensor events. Published reports are snapshot-versioned and reproducible.

## 4. Acceptance

Test row-level/column-level security, k-threshold bypass attempts, export re-identification scenarios, aggregation correctness, stale-data banner, language accessibility and audit completeness. Programme access is reviewed at least quarterly and automatically expires when the programme agreement ends.
