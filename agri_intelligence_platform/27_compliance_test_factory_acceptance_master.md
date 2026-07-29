# AgriGrow Compliance, Test and Factory Acceptance Master Plan

**Document ID:** AGR-QA-027 | **Status:** compliance planning document; accredited laboratory and counsel determine final applicability per SKU/country.

## 1. Per-SKU compliance gate

| Area | Tier 1–3 portable | Tier 4–6 station/control | Owner / release evidence |
|---|---|---|---|
| India radio | WPC/ETA determination for each BLE/Wi-Fi/LoRa/cellular module/configuration | Same plus gateway/radio configuration and antenna | Regulatory owner + lab report/approval record |
| Telecom / IoT | Confirm TEC/MTCTE applicability for the radio/IoT equipment in sale configuration | Confirm cellular/gateway/controller scope | Regulatory owner; current TEC essential-requirement review |
| BIS / safety | Check current QCO/CRS product-category applicability, adapter and supplied PSU | Check device, PSU and any controller category | Compliance matrix signed at DVT/PVT |
| EMC / immunity | Radiated/conducted emissions, ESD, RF coexistence, USB/probe interfaces | Adds surge, EFT, lightning/grounding and long-cable immunity | Pre-scan → accredited test → corrective action |
| Battery / transport | IEC 62133-2/IS-equivalent applicability, UN 38.3 transport evidence, pack protection | LiFePO₄ pack, transport and installation safety evidence | Pack supplier docs + finished-product review |
| Environmental | Stated IP, drop, vibration, thermal/humidity, UV and material tests | Adds mast/wind, solar, corrosion and ingress cable system | Verification report to stated—not aspirational—claim |
| Export | CE/RED/RoHS and FCC/ISED only for target market/SKU | Country-specific radio, EMC, safety and environmental matrix | Export compliance owner |

Current notified categories and requirements change. The regulatory source of truth is the [BIS notified-products list](https://www.bis.gov.in/product-certification/products-under-compulsory-certification/?lang=en), [TEC MTCTE material](https://www.tec.gov.in/public/mandatory-testing-and-certification-of-telecom-equipments-mtcte), WPC process/current notices and accredited-lab advice—not this document.

## 2. Verification specification

| Test group | Sample / condition | Acceptance criterion |
|---|---|---|
| Electrical / charging | Min/nom/max input, hot/cold pack, dead battery, cable fault | No unsafe temperature/current; charging stops outside defined pack-temperature window; event/log captured |
| Firmware / persistence | 1,000 power cuts across commit, update, sync and calibration states | No committed event loss; boot recovery/rollback meets SRS |
| Sensor accuracy | Reference buffers/solutions/instruments across declared range | Meets stated method-specific bias/repeatability; failures are quality-flagged |
| EMC / ESD | Pre-compliance then accredited configuration | No reset/data corruption/unsafe output; corrective action recorded |
| Portable mechanical | Six-face packed drop, button/port/probe cycles, vibration, chemical/sweat | Function, enclosure and calibration stay within declared limits |
| Ingress / dust | Final enclosure, caps, glands and cable system | Only claim tested IP configuration; post-test functional/calibration check |
| Thermal / humidity / UV | Operating/storage extremes, condensation recovery, material ageing | Safe operation/recovery and no unacceptable cosmetic/measurement drift |
| Tower energy / surge | Seasonal simulation, brownout, surge/earth design, cable fault | Energy autonomy model supported; safe restart/buffer; no unsafe actuator path |
| Network / security | Pairing attack, expired credential, replay/stale command, 30-day outage | Authentication/authorisation holds; safe local state; complete audit trail |
| Farmer/operator usability | Target language, elderly/novice, bright sun, gloves and no network | ≥85% guided measurement completion; unsafe misunderstanding is a blocker |

## 3. Factory test and acceptance

Every electronic unit receives a non-reusable serial; electronic device history records component lots, fixture ID/version, operator/time, firmware/SBOM hash, provisioning attestation and test results. Fixtures are calibrated, access-controlled and checked with golden units each shift. Test data is retained for warranty/service lifetime.

| Station | Tests |
|---|---|
| Incoming | Approved-source/lot/PCN check, MSL/ESD handling, critical sensor/probe/battery sample inspection |
| PCB | SPI/AOI/X-ray as package requires; ICT/flying probe: rails, shorts/opens, programming pads |
| Functional | Current profile, display/UI, buttons, USB-C/charge, radio ID, flash, RTC, sensor bus, AFE reference response, secure-boot/debug state |
| Provisioning | Certificate/public ID, signed production image, key-attestation record; private secrets never visible to operator/log |
| Final assembly | Torque/gasket/cable/antenna checks, QR scan, enclosure appearance, probe test, battery health |
| Final acceptance | Calibrated reference response, firmware version, pack/label/manual, sample audit and release signature |

Minimum process criteria: fixture GR&R documented; first-pass yield target agreed before PVT; all critical failures quarantined; recurring defects use FRACAS; no production substitution without approved change control and regression evidence. Factory acceptance tests validate manufacturing function—they do not replace field/lab sensor validation or certification.
