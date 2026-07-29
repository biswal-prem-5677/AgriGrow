# AgriGrow 120-Parameter Benchmark Matrix and Buildability Register

**Document ID:** AGR-BEN-020 | **Version:** 1.0 | **Rule:** Do not represent a score as laboratory evidence.

## 1. How to use this matrix

This is the 120-parameter comparison matrix for the products surveyed in `19_state_of_art_research.md`. It compares the **best public pattern** by product archetype against the AgriGrow requirement. Proprietary products cannot be honestly scored on undisclosed internals; their cells are verified by a later quote, documentation review and hands-on test. `R` means required, `O` optional by tier, `X` intentionally excluded from the tier.

| # | Parameter | Benchmark pattern | AgriGrow decision |
|---:|---|---|---|
| 1 | Farmer entry cost | Premium station/machine | Tier 0/1 shared low-cost path |
| 2 | Shared ownership | Rare | R for Tier 0–3 |
| 3 | Rental workflow | Rare | R for Tier 1–3 |
| 4 | FPO/KVK operator mode | Partial | R |
| 5 | Multilingual field UX | Partial | R |
| 6 | Offline capture | Varies | R |
| 7 | Sunlight-readable UI | Strong handhelds | R Tier 1–3 |
| 8 | Glove operation | Industrial products | R Tier 2–5 |
| 9 | Assisted sampling protocol | Partial | R |
| 10 | Accessibility/voice | Emerging | O, privacy gated |
| 11 | Soil pH method recorded | Often hidden | R |
| 12 | EC cell constant recorded | Research products | R |
| 13 | Soil moisture calibration profile | Research products | R |
| 14 | Probe serial identity | Research products | R Tier 2+ |
| 15 | Calibration expiry gate | Mature instruments | R |
| 16 | Reference-solution workflow | Mature instruments | R Tier 2+ |
| 17 | Raw/derived distinction | Often weak | R |
| 18 | Uncertainty field | Research products | R |
| 19 | Sample medium/depth | Research products | R |
| 20 | Method-specific trend line | Rare consumer UX | R |
| 21 | Lab result linkage | Enterprise FMS | R |
| 22 | Soil texture calibration | Research practice | O/R by use case |
| 23 | Salinity-interference flag | Better soil sensors | R |
| 24 | Temperature compensation | Electrochemical products | R |
| 25 | Sensor warm-up state | Gas/PM leaders | R where relevant |
| 26 | Weather siting metadata | Professional stations | R Tier 4+ |
| 27 | Mast/probe depth metadata | Professional stations | R Tier 4+ |
| 28 | Maintenance record | Enterprise stations | R |
| 29 | Measurement quality flags | Research/industrial | R |
| 30 | Reference instrument comparison | Research | R Tier 4–6 |
| 31 | BLE pairing | Consumer/portable | R Tier 1–3 |
| 32 | Wi-Fi backhaul | Common | O |
| 33 | Cellular backhaul | Stations | O Tier 2, R Tier 4+ SKU |
| 34 | LoRaWAN support | LPWAN products | O Tier 4+ |
| 35 | Private-network support | Industrial IoT | R Tier 5+ |
| 36 | Radio regional plan | Often overlooked | R |
| 37 | Store-and-forward | Mature IoT | R |
| 38 | Idempotent sync | Enterprise cloud | R |
| 39 | Time-source confidence | Research/industrial | R |
| 40 | GNSS/HDOP recording | Professional tools | R Tier 2+ |
| 41 | Solar energy budget | Good stations | R Tier 4+ |
| 42 | Battery service interval | Industrial nodes | R |
| 43 | Power-profile telemetry | Mature fleets | R |
| 44 | Charger thermal protection | Consumer electronics | R |
| 45 | Battery transport evidence | Mature products | R |
| 46 | Power-gated radios | Low-power nodes | R |
| 47 | Brownout recovery | Industrial | R |
| 48 | Lightning/surge strategy | Professional station | R Tier 4+ |
| 49 | Earthing plan | Professional station | R Tier 4+ |
| 50 | Vehicle charging safety | Portable products | R Tier 1–3 |
| 51 | Secure boot | Better industrial IoT | R |
| 52 | Signed OTA A/B rollback | Mature IoT | R Tier 2+ |
| 53 | Unique device key | Mature IoT | R Tier 1+ |
| 54 | Debug lock | Mature IoT | R |
| 55 | Local-data encryption | Strong products | R Tier 2+ |
| 56 | Mutual TLS | Enterprise IoT | R Tier 2+ |
| 57 | QR OOB pairing | Better consumer IoT | R |
| 58 | Key rotation/revocation | Enterprise fleets | R |
| 59 | Signed remote commands | Mature control systems | R Tier 5+ |
| 60 | Audit trail | Enterprise/government | R |
| 61 | IP target | IP66/67 stations common | Tier-specific stated target |
| 62 | Dust test | Industrial products | R Tier 2+ |
| 63 | Rain/condensation design | Stations | R |
| 64 | UV material validation | Better outdoor products | R Tier 2+ |
| 65 | Drop/vibration validation | Portable/industrial | R |
| 66 | Salt/chemical exposure | Specialist products | R by tier |
| 67 | Thermal derating | Industrial | R |
| 68 | Connector cycle test | Professional products | R |
| 69 | Gasket compression control | Mature hardware | R |
| 70 | Spare-part availability | Dealer-led products | R |
| 71 | Replaceable pH/EC probe | Instruments | R Tier 2+ |
| 72 | Replaceable battery | Varies | R where safety validated |
| 73 | Field repair time | Rarely published | Target <10 min basic repair |
| 74 | Calibration consumable supply | Instruments | R |
| 75 | Technician diagnostic package | Enterprise fleets | R |
| 76 | Warranty term | Market varies | Publish by SKU |
| 77 | End-of-support policy | Rare | R |
| 78 | E-waste/recovery route | Emerging | R |
| 79 | Repair documentation | Open products | R tier-appropriate |
| 80 | Counterfeit probe control | Research-grade | R |
| 81 | Local edge rules | Mature automation | R |
| 82 | TinyML anomaly detection | Emerging | O, measured benefit required |
| 83 | Vision capture | Stations/machines | O Tier 3+ |
| 84 | Vision model provenance | Better systems | R if vision used |
| 85 | Model confidence | Emerging | R |
| 86 | Model applicability zone/crop | Better agronomy stacks | R |
| 87 | Human escalation | Service platforms | R |
| 88 | Model rollback | Mature MLOps | R |
| 89 | Tool-call safety | Emerging LLM systems | R |
| 90 | Advisory expiry | Better alert systems | R |
| 91 | Valve/pump local controller | Industrial irrigation | R Tier 5+ |
| 92 | Manual override | Industrial control | R Tier 5+ |
| 93 | Stale-command rejection | Safety control | R Tier 5+ |
| 94 | Flow/pressure feedback | Mature irrigation | R Tier 5+ |
| 95 | Fail-closed mode | Safety control | R Tier 5+ |
| 96 | Pesticide actuation | High-risk | X until separate safety case |
| 97 | Fertigation control | Mature but complex | Needs engineering |
| 98 | Drone integration | Enterprise | O API/data only |
| 99 | Robot autonomy | Research/enterprise | Research stage |
| 100 | Safety certification path | Industrial control | R before actuation sale |
| 101 | Event schema version | Mature cloud | R |
| 102 | Data lineage | Research/enterprise | R |
| 103 | Cross-tier comparability rules | Rare | R |
| 104 | Tenant isolation | Enterprise SaaS | R |
| 105 | Consent/purpose access | Emerging | R |
| 106 | Farmer export/correction | Strong privacy products | R |
| 107 | Research de-identification | Mature data platforms | R |
| 108 | Government aggregation threshold | Public-sector systems | R |
| 109 | Sampling-bias display | Rare | R |
| 110 | Marketplace/advisory separation | Rare | R |
| 111 | First-article traceability | Mature EMS | R |
| 112 | Fixture GR&R | Mature manufacturing | R |
| 113 | Supplier alternate control | Mature hardware | R |
| 114 | SBOM | Security leaders | R |
| 115 | Manufacturing test coverage | Mature hardware | ≥95% testable faults |
| 116 | Field validation zones | Research programmes | ≥3 before scale claim |
| 117 | Certification matrix | Mature products | R per SKU |
| 118 | Cost transparency | Rare | R planning/contract level |
| 119 | Programme deployment playbook | Mature public systems | R Tier 7+ |
| 120 | Federated national model | Rare | R; no central raw-data default |

## 2. Buildability register

| Feature | Classification | Reason and release rule |
|---|---|---|
| Tier 0 manual pH/EC/sample kit | READY TODAY | Commercial kits, QR workflow and trained sampling protocols exist; label as screening/manual. |
| Tier 1 BLE handheld | READY TODAY | Low-power MCUs, display, battery and basic probes are available; validate expectations/cost. |
| Tier 2 secure handheld pH/EC/moisture/GNSS | READY TODAY | Engineering integration plus calibration/service required; do not claim lab equivalence. |
| Replaceable-probe identity and calibration workflow | READY TODAY | Standard secure EEPROM/QR and event-provenance patterns. |
| Offline encrypted events and signed OTA | READY TODAY | Proven embedded/cloud patterns; needs engineering discipline. |
| Tier 3 shared professional backpack kit | NEEDS ENGINEERING | Hardware is available; chain-of-custody, operator consistency and service workflow need field design. |
| Tier 4 solar weather/soil tower | READY TODAY | Existing commercial products prove feasibility; Indian siting/energy/maintenance needs engineering. |
| Private LoRaWAN farm network | READY TODAY | Products/software exist; radio survey, gateway O&M and regional compliance required. |
| Tier 5 supervised irrigation controller | NEEDS ENGINEERING | Components exist; local safety design, commissioning and liability process are substantial. |
| Bounded AI irrigation recommendation | NEEDS ENGINEERING | Requires crop/soil/weather validation and outcome data, not only ML. |
| Disease-risk forecast | NEEDS ENGINEERING | Practical for specific crop/region/pathogen only after local validation. |
| Edge vision for scouting | NEEDS ENGINEERING | Cameras/models exist; Indian crop lighting/labels/privacy must be verified. |
| Machine vision targeted spraying | NEEDS ENGINEERING | Proven in high-capex machines; crop/nozzle/safety/FTO barriers block near-term smallholder product. |
| Tier 6 reference station | READY TODAY | Buy/integrate traceable commercial instruments; research operating practice is the constraint. |
| Tier 7 district monitoring | NEEDS ENGINEERING | Hardware exists; governance, coverage design, calibration and operations are the main work. |
| Tier 8/9 federation | NEEDS ENGINEERING | APIs/security are mature; institutional agreements, standards and trust are hard. |
| Direct in-field N/P/K readings | RESEARCH STAGE | Interference, extraction chemistry, soil variation and calibration prevent generic consumer claim. |
| Organic carbon / microbial-health instant probe | RESEARCH STAGE | Needs validated analytical method and reference datasets. |
| Heavy-metal/water contamination field claim | RESEARCH STAGE | Screening possible; regulated decisions need laboratory-confirmed methods. |
| Hyperspectral handheld diagnosis | RESEARCH STAGE | Sensors exist but robust crop/condition calibration and economics are not established. |
| Battery-free buried multi-year sensor swarm | RESEARCH STAGE | Energy harvesting/communications are promising but not dependable baseline. |
| Fully autonomous pesticide/fertiliser action via LLM | UNREALISTIC TODAY | Safety, legal, model reliability and actuation verification are unacceptable. |
| One universal cheap “soil health” sensor | UNREALISTIC TODAY | Soil health is multi-method, not a single physical quantity. |
| National real-time raw farm-data lake | UNREALISTIC TODAY | Governance, representation, privacy and operating cost make it an unsafe architecture goal. |

**Decision rule:** “Needs engineering” is not permission to market. It moves to READY TODAY only after its written acceptance evidence in the validation plan is passed.
