# AgriGrow Testing and Validation Plan

**Document ID:** AgriGrow-VV-013 | **Version:** 1.0

## 1. Verification strategy

Requirement evidence is classified as inspection (I), analysis (A), demonstration (D) or test (T), with traceability from PRD/SRS ID to test case, fixture/software version, operator, raw result, deviation and approval. A pass in a lab never substitutes for agronomic field validation.

| Level | Key evidence |
|---|---|
| Component | Sensor lot characterisation, AFE noise/leakage, battery/charger, display sunlight, connector cycles, radio sensitivity. |
| Board/device | ICT/flying-probe, boundary scan where available, functional fixture, current profile, thermal, ESD/EMC pre-scan, ingress/drop/vibration. |
| Firmware/app/cloud | Unit/integration/contract tests, power-cut persistence, OTA rollback, security-negative tests, load/replay/DR and accessibility. |
| System field | Protocol adherence, reference instruments/lab comparison, network/offline journeys, language usability, service/repair and seasonal/environmental trials. |

## Tier-system conformance

| Tier family | Release evidence beyond common tests |
|---|---|
| 0–1 | Assisted-user comprehension, comparator/strip lot and expiry control, protocol/scanning error study, safe disposal/replenishment. |
| 2–3 | Portable accuracy/repeatability, probe interchangeability, power-cut/offline sync, drop/ingress, calibration and technician-service trials. |
| 4 | Solar energy autonomy by season/location, mast and sensor siting, lightning/surge/earthing, remote health, weather-reference comparison and 30-day communications loss. |
| 5 | Radio coverage/capacity, gateway outage, sensor density and topology, actuator isolation, stale-command, manual override and local fail-safe tests. |
| 6 | Traceable reference chain, calibration certificates, raw-channel retention, experiment reproducibility and independent laboratory comparison. |
| 7–9 | Cross-tenant/federation security, aggregation/suppression, coverage-bias reporting, disaster recovery, policy/audit and interoperability conformance. |

No product tier may inherit an accuracy, IP rating, battery life, radio range or autonomous-control claim from another tier. A common enclosure, sensor family or cloud endpoint does not constitute evidence.

## 2. Measurement validation

For pH, use traceable buffers across operating range, multiple temperatures, electrode ageing and field slurry protocol; report bias, repeatability, reproducibility and calibration drift. For EC, use certified reference solutions and range/cell-constant checks. For soil moisture, compare each probe/algorithm with gravimetric VWC across soil textures, salinity bands, compaction and depths; publish where performance is unsupported. Do not validate a sensor solely against another unvalidated handheld.

The field trial must span at least three agro-climatic zones before national-scale claim, include novice and extension-worker operators, and log sampling protocol deviations. Acceptance limits are pre-registered per method and may be tightened after pilot learning; results outside limit produce a product limitation or design change, not a cosmetic calibration offset.

## 3. Environmental and reliability tests

Perform temperature/humidity operating/storage cycling, UV exposure, salt/dust/water ingress appropriate to stated IP target, 1 m packed drops in multiple orientations, transport vibration, button/port/probe mating cycles, battery charge/discharge/abuse evidence, and corrosion/chemical exposure to likely farm contaminants. HALT identifies design margins; HASS screens production only after correlation to real failure modes. Validate gasket compression, membrane contamination and post-test calibration.

## 4. FMEA starter register

| Failure mode | Effect | Detect / contain | Initial action |
|---|---|---|---|
| pH electrode dries/contaminates | Biased reading | Slope/offset check; calibration expiry | Storage cap, rinse guidance, consumable replacement |
| Moisture affected by salinity | False irrigation conclusion | Contextual EC/quality flag | Region-specific calibration; limit recommendation |
| Condensation at vent | RH/VOC error | Plausibility/self-test | Membrane, thermal separation, recovery timeout |
| Flash interrupted write | Lost/partial event | CRC + two-phase commit | Recover last valid segment; retain diagnostic |
| OTA power loss | Bricked device | A/B boot confirmation | Automatic rollback/recovery |
| Account/QR takeover | Wrong-field data exposure | OOB code, expiring binding | Revoke, transfer audit, recovery flow |
| Supplier part change | Drift/EMC/reliability regression | AVL/change control | Requalification and lot traceability |

## 5. Release gates

EV proves architecture; DV proves design/specification; PV proves manufacturing process and field workflow. No PVT until all critical/high FMEA actions are closed or risk accepted by accountable owner, certification plan is agreed with labs, security review is passed, measurement validation is documented, and service/repair pilot is successful. Production releases require first-article inspection, fixture GR&R, traceable calibration equipment, golden-device regression and lot acceptance sampling.
