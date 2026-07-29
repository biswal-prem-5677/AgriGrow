# AgriGrow Tier 5–9 Network, Control and Federation SRS

**Document ID:** AGR-SYS-024 | **Principle:** Observe first; control only through a local safety system; federate only authorised aggregates.

## 1. Tier 5 Multi-Tower IoT Network

| Component | Requirement |
|---|---|
| Topology | 5–50 Tier 4 nodes per managed farm/network; private LoRaWAN where radio survey supports it, cellular fallback, authenticated edge gateway, local MQTT bridge and secure cloud connector. |
| Gateway | Industrial Linux gateway with TPM/secure boot, UPS/solar option, VPN/mTLS, 7-day local buffer, remote-update A/B partition and no direct public inbound ports. |
| Camera node | Fixed RGB/thermal/multispectral only after crop/privacy purpose approval; signed image metadata includes calibration target, illumination/aim, model version and retention rule. |
| Actuation boundary | Separate controller enclosure owns valves/pump/fertigation. Network gateway cannot energise output directly. Commands must be signed, scoped, expiring, sequenced and confirmed by local controller. |
| Local controls | Manual OFF/AUTO selector, physical emergency stop where applicable, fuse/contactors, dry-run/flow/pressure/level interlocks, maximum run time, alarm output and safe schedule fallback. |
| Cybersecurity | Device identity, role/purpose access, network segmentation, gateway allow-list, signed configurations, security logs, annual pen test and incident runbook. |

### Irrigation command state machine

`REQUESTED → policy validated → local interlocks checked → operator approval (where required) → ARMED → RUNNING → flow/pressure verified → COMPLETE/FAULT → immutable audit event`.

Any missing sensor, stale weather/soil data, gateway loss, clock discrepancy, valve feedback fault or emergency stop moves the controller to `FAULT` or its locally configured safe schedule. No language model, dashboard, mobile app or cloud rule is permitted to bypass this state machine.

## 2. Tier 6 Research-Grade Sensor Station

Tier 6 is a controlled measurement site, not merely a more expensive tower. It requires traceable reference instruments, calibration certificates, raw-channel capture, controlled installation, experiment design, independent lab linkage and a qualified operator. Recommended interfaces are SDI-12/RS-485/Modbus plus calibrated analogue channels with isolation. Maintain a reference log of calibration date/standard/technician, instrument serial, firmware and environmental conditions.

Minimum station: research VWC/temperature/EC or water-potential profile; Class-appropriate weather head; reference rain/wind; calibrated data logger; UPS/solar/mains design; laboratory pH/EC comparison rig; secure raw-data archive. Every processed dataset links to raw data, algorithm commit, calibration version and exclusion criteria.

## 3. Tier 7 District Monitoring Station

District deployment contains reference stations, sample/FPO fleet, service inventory, calibration kit, operator training and a district operations console. It does not expose individual farm locations by default. Dashboard renders coverage, sample count, method mix, calibration freshness, missingness and sampling bias beside every indicator. District alerts require a named duty officer, source/provenance and communication/withdrawal workflow.

## 4. Tier 8 State Grid and Tier 9 National Federation

| Requirement | Tier 8 state grid | Tier 9 national federation |
|---|---|---|
| Architecture | State tenant/data steward, local analytics and programme APIs | Federated catalogues/standards and authorised cross-state aggregate exchange |
| Data | Minimum necessary raw/pseudonymous data under state policy | Aggregate/de-identified data by default; no central copy of all farm records |
| Identity | State programme roles, purpose and retention | Cross-state trust registry, signed metadata and revocation |
| Interoperability | Versioned observation, calibration and advisory APIs | Conformance suite, vocabulary/profile registry and semantic-version governance |
| Resilience | State DR, audit and access review | Independent federated DR exercises and national incident coordination |
| Accountability | Named state data steward and technical owner | Multi-party standards/privacy/security governance board |

No Tier 8/9 system shall calculate a regional conclusion without displaying sampling coverage, measurement profile eligibility, confidence, geographic/time aggregation and known bias. Public release uses disclosure controls, k-thresholds, differential/generalisation techniques where appropriate and independent re-identification review.

## 5. Tier 5–9 acceptance gates

- Tier 5: radio survey, control-system hazard analysis, electrical inspection, dry-run/flow fault injection, manual override, 30-day network outage, cybersecurity and operator drill.
- Tier 6: traceability audit, calibration/lab comparison, raw-data reproducibility and research ethics/data-access approval.
- Tier 7: programme agreement, training/service capacity, bias/coverage design, aggregate-security test and public-alert drill.
- Tier 8/9: legal/purpose agreements, interoperability certification, tenant isolation, privacy assessment, audit/DR exercise and governance-board release.

Tier 5 pumps/valves can be commercial only after a product-specific safety case and applicable electrical/control compliance review. Tier 6–9 cannot be declared “national infrastructure” by technical launch alone; their legitimacy requires institutionally authorised governance and independent evidence.
