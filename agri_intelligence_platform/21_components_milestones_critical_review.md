# AgriGrow Component Strategy, Milestones and Critical Design Review

**Document ID:** AGR-ENG-021 | **Version:** 1.0 | **Cost basis:** indicative INR/unit, ex-GST, at ~10k-unit procurement unless stated

## 1. Sourcing rules before a BOM is frozen

The table covers active, precision, power, radio, display and safety-critical parts—not every resistor, capacitor, screw or gasket. Commodity passives are controlled through a specification/approved-vendor list (rating, dielectric, tolerance, AEC/industrial requirement where applicable, alternate manufacturer, MSL and traceability), not a single manufacturer part number. Prices, stock, Indian/Chinese availability and lead time are volatile; every value below is a planning range, not a purchase quote.

Source through authorised distributors or direct manufacturer allocation for production: **India:** Arrow/Avnet/element14/Mouser India or EMS-approved channel; **China/Asia:** manufacturer-authorised channel, LCSC only for non-strategic prototype parts, and EMS-approved local distributors. No marketplace-only source is allowed for security, radio, power, calibration or safety-critical parts. “Available” means a qualified supply path can be sought, not that stock is currently committed.

## 2. Critical component candidate register

| Function | Manufacturer / model / datasheet | 10k planning cost | India / China source plan | Lead-time & EOL risk | Qualified alternative / upgrade |
|---|---|---:|---|---|---|
| Main MCU | [ST STM32U585AI](https://www.st.com/resource/en/datasheet/stm32u585ai.pdf) | 650–1,050 | Authorised ST distribution / EMS allocation | Medium: secure MCU allocation and package risk | STM32U575, NXP MCX N; freeze after firmware/security port review |
| BLE radio | [Nordic nRF52840](https://docs.nordicsemi.com/r/bundle/ps_nrf52840/) or certified module | 350–750 | Nordic authorised distributor; China module manufacturer only after RF requalification | Medium: module certification/antenna dependency | nRF5340 module for dual-core/longer roadmap; exact radio SKU needs WPC/ETA review |
| Wi-Fi option | Espressif ESP32-C6-MINI-1 | 200–380 | Official/authorised distribution; broad China ecosystem | Low–medium: module variant/factory test risk | ESP32-S3 module; use only a power-gated optional SKU |
| Cellular option | Quectel BG95-M3 / regional certified module | 1,400–2,600 | Direct/authorised Quectel channel; operator/certification partner | High: module lifecycle, carrier bands, SIM and certification | Cat-1 bis regional module after district/operator test; do not freeze on catalogue alone |
| GNSS | u-blox MAX-M10S + tuned antenna | 500–900 | u-blox authorised channel / EMS AVL | Medium: RF/antenna and allocation | Quectel LC29H family after accuracy/power/RF test |
| Temp/RH | [Sensirion SHT41](https://sensirion.com/products/catalog/SHT41) | 120–220 | Sensirion authorised distributor | Low–medium: small package/handling | SHT45 for accuracy tier; require vent/thermal test, not drop-in claim |
| Pressure | [Bosch BMP390](https://www.bosch-sensortec.com/en/products/environmental-sensors/pressure-sensors/pressure-sensors-bmp390.html) | 70–140 | Bosch authorised distributor | Low–medium | Infineon DPS310; rerun calibration/current tests |
| Light / UV | Vishay VEML7700 + VEML6075 | 90–180 | Authorised distributor / China channel with incoming inspection | Medium: window, calibration and package substitutions | ams OSRAM equivalent; product-level optical calibration required |
| QSPI flash | Winbond W25Q128JV | 80–150 | Multiple authorised channels | Low: multi-source after firmware qualification | Macronix MX25L128, GigaDevice GD25Q128 |
| Secure element | Microchip ATECC608B-TNGTLS | 120–240 | Microchip authorised distribution | Medium: provisioning process more critical than stock | MCU secure storage + secure element alternate after threat-model review |
| USB-C charger / power path | TI BQ24074 or qualified 1S power-path charger | 100–220 | TI authorised distribution | Medium: charger thermal/pack qualification | MCP73871; validate JEITA, USB-C and load-sharing behaviour |
| Fuel gauge | ADI/MAX17048 | 90–170 | ADI authorised distribution | Low–medium | TI BQ27441; requires battery profile verification |
| Buck/boost rails | TI TPS63070-class converter | 90–190 | TI authorised channel | Medium: inductor/layout availability | MPS/ADI alternate after EMC and transient test |
| Display | Sharp 2.7-in memory-in-pixel class module | 500–850 | Display manufacturer/EMS channel | High: display-life and MOQ | Reflective/transflective LCD module; UI/redesign and sunlight test required |
| pH AFE | TI LMP91200-class electrometer AFE + guarded board | 180–400 excluding electrode | Direct/authorised channel; specialist analogue design partner | High: leakage/cleanliness/design risk, not merely part EOL | Discrete electrometer op-amp architecture; full validation rerun |
| pH electrode | Industrial double-junction replaceable combination electrode | 700–1,400 | Indian lab-instrument supplier + qualified global OEM | Medium–high: consumable, storage and lot variability | ISFET cartridge only after chemistry/cost validation |
| EC cell | Four-electrode AC conductivity cell | 450–1,000 | Laboratory/industrial probe supplier | Medium: cell constant/connector/temperature metadata | Two-electrode cell only for narrow low-cost range with restrictions |
| Moisture probe—Tier 2 | Coated FDR/capacitance probe, AgriGrow-qualified | 500–1,100 | Indian/China manufacturing partner with calibration samples | High: soil/salinity/drift risk | [Vegetronix VH400](https://www.vegetronix.com/Products/VH400/) as benchmark; custom probe needs gravimetric validation |
| Moisture probe—Tier 4/6 | [METER TEROS 12](https://metergroup.com/products/teros-12/) reference option | ~US$271 public base price | METER/distributor quote | Medium: premium cost/import lead time | Acclima/other SDI-12 research probe, with comparison study |
| Battery pack | 1S 4,000 mAh Li-ion pouch + PCM/NTC from qualified pack assembler | 450–750 | Indian pack assembler with cell traceability; dual Asian cell sources | High: safety, transport, cell allocation | LiFePO₄ for tower; pack-level UN38.3/safety evidence required |
| Tower power | 20–40 W solar panel + LiFePO₄ + industrial MPPT | 4,000–9,000 | Indian solar/EMS suppliers | Medium: outdoor quality and seasonal energy margin | Higher-capacity LiFePO₄; test by site/season, no generic autonomy claim |

### Component acceptance policy

1. Obtain manufacturer PCN/EOL policy, authorised-source traceability, moisture-sensitivity/reflow requirements, counterfeit-control declaration and 12-month forecast before PVT.
2. Apply a two-source strategy only after form/fit/function, RF/EMC, power, firmware, measurement and certification impact are tested. “Pin-compatible” is not automatically qualified.
3. Treat probes, display, battery, cellular module and secure provisioning as strategic parts with an approved alternate and buffer plan.
4. Keep an engineering BOM, approved vendor list, AVL, manufacturer lifecycle status, country-of-origin and test impact in PLM. An unauthorised substitution blocks production.

## 3. Milestone plan

| Milestone | Objective and configuration | Budgeted programme cost | Expected problems | Validation / exit |
|---|---|---:|---|---|
| Research harness (0–3 months) | Benchtop pH/EC FEs, three moisture candidates, T/RH/light/pressure, reference instruments; no product enclosure | INR 4–8 lakh | pH leakage/noise, EC polarisation, moisture/salinity error | Noise/leakage characterisation; buffer/reference/gravimetric comparison; kill weak sensor choices |
| Prototype 1 / EVT (3–6 months) | 10–20 Field Scout alpha units, dev boards/custom AFE, BLE, local event format, 3D-printed enclosure | INR 12–22 lakh | Battery/runtime shortfall, antenna detuning, probe damage, confusing workflow | Guided-use test, current profile, power-cut persistence, preliminary drops/ESD and calibration repeatability |
| Prototype 2 / DVT (6–10 months) | 50–100 custom 6-layer units, industrial enclosure candidate, production firmware, fixture v1, phone app | INR 30–55 lakh | EMI, ingress/gasket, display sourcing, calibration workflow adherence | DFM/DFT, EMC pre-scan, environmental/ingress/drops, 3-zone reference comparison and repair task test |
| Prototype 3 / field pre-pilot (10–15 months) | 200–300 Tier 2 units plus 10 Tier 3 kits and 5 Tier 4 towers | INR 0.8–1.5 crore | Seasonal drift, rural support, sync/backhaul, installation quality | 90-day field reliability, calibration compliance, farm/FPO usability, tower energy/radio/maintenance evidence |
| Pilot deployment (15–24 months) | 1,000 Tier 1/2/3 assets and 25–50 towers with KVK/FPO partners | INR 2–4 crore | Service cost, loss/damage, data-quality bias, demand uncertainty | Unit economics, repair turnaround, multi-zone accuracy, partner training and SLO/DR audit meet gates |
| PVT / commercial launch | 1,000–5,000 controlled production units; Tier 4 only with surveyed installation | Separate working-capital/certification/tooling approval | Yield, test escapes, supplier variance, launch support | First-article/fixture GR&R, certification evidence, burn-in/field acceptance, warranty reserve and launch-readiness review |

Budgets include programme-level engineering/fixtures/field activity ranges, not a binding proposal. They exclude a full national rollout, government tender cost, land/civil works, taxes and marketing. Stop or redesign if measurement validity, safe service economics or user trust fails; do not “pilot through” a failed core assumption.

## 4. Critical review (simulated expert lenses)

This is a disciplined internal review using the requested perspectives. It does **not** claim review or endorsement by Apple, John Deere, Bosch, ISRO, ICAR or any named organisation.

| Review lens | Likely criticism | Redesign decision |
|---|---|---|
| Premium hardware/product team | One handheld trying to contain pH, EC, gas, PM, camera, radio and voice will be expensive, fragile and impossible to explain. | Freeze Tier 2 to soil/water/ambient core; use a physical accessory taxonomy for gas/PM/camera and a separate Tier 4 station. |
| Agricultural machine-control engineers | AI/cloud instructions cannot safely operate pumps/valves, and a sensor failure can water the wrong zone. | Tier 5 uses independent local controller, manual override, flow/pressure feedback, expiry/replay protection and fail-closed rules. |
| Sensor engineers | Specifications ignore installation, drift, contamination, salinity, condensation and thermal self-heating. | Put installation/method/calibration into data schema, ship reference consumables, and gate advice on quality state. |
| Space/remote-field systems engineers | Rural power, heat, lightning, radio loss and repair logistics exceed lab assumptions. | Tower energy design uses seasonal margin, LiFePO₄/solar, surge/earthing, store-and-forward, health telemetry and field-replaceable modules. |
| Indian agricultural scientists | Direct “soil health/NPK” claims could harm fertiliser decisions and conflict with disciplined sample/lab practice. | Tier 0–3 support sampling/protocol/lab linkage; NPK/OC/microbial results remain research/lab-linked until independent validation. |
| Startup investors | Hardware margins disappear under calibration, support, channel and warranty costs; farmer CAC is high. | Lead with FPO/KVK/enterprise service channels, shared ownership and paid O&M; measure contribution after support, not shipment revenue. |
| Manufacturing experts | High-impedance AFE, RF, battery and outdoor enclosure make a generic EMS quote unsafe. | Use NPI gates, specialist design reviews, test fixtures, controlled provisioning, AVL/PCN discipline and a dedicated reliability budget. |

### Top risks and non-negotiable mitigations

| Risk | Severity | Early indicator | Mitigation / decision gate |
|---|---|---|---|
| Invalid soil moisture recommendation | Critical | Error varies by texture/salinity/depth | Soil-specific reference study; label relative readings; prohibit hectare-wide automation without valid profile. |
| pH/EC probe service failure | High | Calibration slope/offset drift, user rinse/storage failure | Consumable workflow, expiry gate, technician swap and no “valid” advisory on expired calibration. |
| Station energy/radio failure | High | Battery low/queue backlog/retries | Seasonal energy model, radio survey, site acceptance and remote health; install no tower without margin. |
| Tier 2 price exceeds farmer value | High | Low usage after purchase, repair cost, FPO preference | Protect Tier 0/1/shared routes; defer premium sensors and prove value with paid pilot. |
| Poor manufacturing yield | High | ICT/functional failures, rework trend | DFM/DFT before tooling, golden units, GR&R, line pilot and supplier corrective action. |
| AI overreach/unsafe advice | Critical | High override/complaint, low confidence/missing inputs | Bounded policy, provenance, confidence, human escalation and kill switch. |
| Data misuse/public distrust | Critical | Excessive export/query, consent confusion | Purpose-based access, aggregate default, audit and independent privacy review. |
| Competitor/IP conflict | High | Overlapping claims/feature roadmap | FTO counsel before Tier 5 vision/control or public launch; focus claims on distinct provenance/service inventions. |

## 5. Redesigned launch architecture

**Launch only three coherent offers:**

1. **Tier 0 Soil Test Kit:** trained sampling/manual screening + QR protocol + lab/KVK linkage.
2. **Tier 2 Field Scout S1:** serviceable spot pH/EC/moisture/temperature/ambient device, offline app, calibration/probe workflow and no direct nutrient claim.
3. **Tier 4 Solar Farm Tower:** separately installed, solar-powered soil/weather reference node for FPO/enterprise pilots; no actuation in its first commercial release.

Tier 1 is a later cost-down derivation once a smaller measurement set is validated. Tier 3 is an operational packaging of proven probes/workflow for shared professionals. Tier 5 actuation, Tier 6 research stations and Tier 7–9 programme systems start only after the three launch offers meet measurement, support and economics gates. This preserves the national vision while preventing a single first release from becoming an unserviceable collection of promises.
