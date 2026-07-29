# AgriGrow State-of-the-Art Research Landscape

**Document ID:** AGR-RES-019 | **Research cut-off:** 2026-07-29 | **Status:** Design-input survey, not freedom-to-operate, procurement, or investment advice

## 1. Scope and method

“Every existing solution worldwide” is not a finite, verifiable catalogue. This document therefore benchmarks 18 traceable products and platforms across the relevant archetypes: machine vision/actuation, fixed sensing, soil instruments, IoT networks, portable tools, Indian precision platforms, post-harvest intelligence, and open source. Public specifications are used; undisclosed architecture, battery life, accuracy and pricing are marked **not public / quote** rather than inferred. A formal competitor audit must add regional dealer interviews, a hands-on test plan, customer references, pricing quotes and teardown/FTO work.

## 2. Curated global product benchmark

| Company / product / country | Target customer | Hardware architecture and sensors | Features / AI | Connectivity / power / public price | Strengths | Gaps, adoption challenge and AgriGrow comparison |
|---|---|---|---|---|---|---|
| [John Deere See & Spray](https://www.deere.com/en-us/products-solutions/sprayers-and-applicators/see-spray) / US | Large row-crop operators | Boom-mounted cameras, vision processors, individual nozzle control, integrated sprayer | Crop/weed vision, targeted application, field insights | Machine power; proprietary machine/cloud; machine/upgrade quote | Production-grade edge vision and dealer service | Expensive, tractor/sprayer dependent, crop/market-specific; AgriGrow should use its safety isolation and evidence concepts, not promise Tier 2 actuation. |
| [Trimble precision stack](https://agriculture.trimble.com/) / US | Mechanised farms/OEMs | GNSS displays, guidance, steering, implement controllers | Guidance, variable-rate/field workflows | Vehicle power; cellular/Wi-Fi ecosystem; quote | Mature machine integration | Not a low-cost smallholder sensor pathway; AgriGrow needs open event provenance and portable-first access. |
| [Topcon agriculture](https://www.topconpositioning.com/agriculture) / Japan/US | Professional machine operators | GNSS, displays, steering, implement control | Precision guidance/application | Vehicle power; dealer ecosystem; quote | Rugged machine-control heritage | High capex and retrofit/integration complexity; only Tier 5+ is comparable. |
| [CropX](https://cropx.com/) / Israel | Farms, advisors, agribusiness | Soil sensors, telemetry, rain/weather/ET and third-party integrations | Agronomy/FMS and irrigation-oriented decisions | Cellular/telemetry; installed; quote | Software plus multiple sensor types and integration | Subscription/service and installation burden; AgriGrow differentiates with assisted Tier 0–3 and India governance. |
| [Arable Mark 3](https://www.arable.com/mark3/) / US | Commercial farms/research | Solar cellular field station, weather/plant/soil context, 5 MP camera | Crop intelligence, imagery and models | Solar battery + cellular; quote | Integrated IP67 sensing/camera station | High-end fixed-station economics and proprietary data path; informs Tier 4, not farmer entry. |
| [METER TEROS 12 + ZL6](https://metergroup.com/products/teros-12/) / US | Research and precision irrigation | 70 MHz moisture, temperature, EC probe; logger/cloud | High-quality profile sensing and verification | SDI-12/logger; low power; TEROS 12 public base price US$271 | Strong soil-physics pedigree, durability and installation tooling | Per-sensor cost, skilled installation and no low-cost handheld route; Tier 6 benchmark and Tier 4 accessory option. |
| [Pessl iMETOS](https://metos.global/) / Austria | Orchards, vineyards, crop advisers | Field weather stations, disease/irrigation modules | Microclimate/disease-risk decision support | Solar/cellular/LoRa variants; quote | Mature weather/disease focus | Requires station siting/maintenance and crop-model localisation; AgriGrow must validate Indian crop models. |
| [Teralytic](https://www.teralytic.com/) / US | Soil-focused growers | Multi-depth soil probe with wireless network | Soil data dashboard/advice | Battery/wireless; quote | Dense soil-profile concept | Installation/soil-specific interpretation and cost; avoid claiming universal soil chemistry. |
| [Farm21](https://farm21.com/) / Netherlands | Farms and supply-chain programmes | Wireless soil/weather nodes and gateway | Monitoring and decision support | LPWAN/cellular; quote | Simple deployment orientation | Sensor density, radio coverage and service still drive TCO; validate per district. |
| [SenseCAP Agriculture](https://www.seeedstudio.com/solution/agriculture/) / China | Integrators, farms, pilots | LoRaWAN nodes/gateway: soil, weather, CO₂, vision/DTU modules | Device cloud/API, some TinyML vision | LoRaWAN, Ethernet/Wi-Fi/LTE backhaul; battery nodes; public retail varies | Fast modular industrial IoT deployment | Commodity integration does not prove agronomic calibration, Indian radio/certification or long-term support. |
| [Libelium Smart Agriculture](https://www.libelium.com/iot-solutions/smart-agriculture/) / Spain | System integrators | Sensor-node/gateway platform with agriculture probes | IoT integration and analytics hooks | LPWAN/cellular options; quote | Broad industrial integration | Integration kit, not a validated farmer product; service and calibration remain customer responsibility. |
| [Vegetronix VH400](https://www.vegetronix.com/Products/VH400/) / US | DIY/professional irrigation users | 3-wire analogue transmission-line moisture probe | Spot/continuous VWC measurement | 3.5–20 V, <13 mA; direct purchase | Simple rugged low-cost interface | Needs local calibration/integration; no farmer workflow/provenance platform. |
| [Acclima TDR-315](https://acclima.com/) / US | Research/irrigation | TDR soil moisture/EC/temperature probe | High-quality soil measurement | Logger/SDI-12-class integrations; quote | Strong measurement method | Premium cost and installation requirements; Tier 6 reference comparator. |
| [GroGuru WUGS](https://groguru.com/) / US | Irrigated commercial farms | Soil sensors + wireless gateway/cloud | Irrigation recommendations | Wireless/cellular; subscription/quote | Water-management focus | Narrow domain and field-installation economics; AgriGrow needs wider but bounded platform. |
| [Fasal](https://www.fasal.co/fasal-story) / India | Horticulture, enterprises and growers | Weather station, soil moisture and irrigation automation hardware | Crop/stage advisory, disease/pest risk, automation | Field connectivity; solar/station; public price historically reported around INR 30k but obtain current quote | India-native deployment, multilingual agronomy and automation | Direct Tier 4/5 competitor; AgriGrow must not duplicate without superior calibration, open provenance and service evidence. |
| [AgNext Qualix](https://agnext.com/) / India | Agribusiness procurement/processors | AI/spectral/image quality-assessment hardware plus SaaS | Rapid commodity quality assessment and trade records | Mains/portable varies; enterprise quote | Strong post-harvest quality/trade focus | Not a soil/field network; potential interoperable marketplace/quality partner rather than copy target. |
| [DeHaat](https://dehaat.in/) / India | Smallholders, FPOs, input/market ecosystem | Primarily a service/commerce/advisory platform; hardware details not public | Inputs, soil testing, advisory, drones, finance/market links | Mobile/service network; public hardware price not applicable | Dense field/channel distribution | Sensor/provenance architecture not public; AgriGrow can integrate carefully but must avoid conflicted input steering. |
| [FarmBot](https://farm.bot/pages/open-source) / US | Education, gardens, controlled beds | Open CAD, stepper gantry, camera/tool mount, sensors | Automated bed farming and software | Mains + network; kit price varies | Open hardware/software and repairability | Not rugged broad-acre hardware; borrow openness and tool-interface discipline, not its form factor. |

### Product-level conclusions

1. **Commercial fixed monitoring is ready.** Arable, Pessl, CropX, SenseCAP and Fasal demonstrate credible Tier 4 patterns: solar, weather/soil sensing, radio backhaul and remote dashboards.
2. **Accurate soil measurement is costly and protocol dependent.** METER/Acclima style products validate the need for installation, calibration, verification and stated limits. A cheap sensor cannot inherit their research credibility.
3. **Closed-loop farm control is a Tier 5 safety product.** Deere proves edge vision/actuation at industrial scale; AgriGrow must retain an independent local safety controller, manual override and signed bounded requests.
4. **Platform advantages are service and trust, not another dashboard.** India already has capable digital/commerce and IoT players. AgriGrow’s defensible gap is cross-tier data quality, assisted adoption, repair/calibration, consent and public-interest federation.

## 3. Precision-agriculture startups and deployments

| Segment | Representative evidence | Design lesson |
|---|---|---|
| Soil + FMS | CropX joins sensors, weather, ET, machinery and farm management. | Preserve external sensor/machinery adapters; do not force a hardware monoculture. |
| Fixed crop intelligence | Arable combines weather, plant/soil context and daily camera imagery in one solar cellular station. | A camera must be installed with a purpose, privacy zone and model/lighting validation plan. |
| India farm autonomy | Fasal describes field weather/soil sensing, crop models and irrigation/fertigation automation. | Compete on validated local agronomy and service economics, not feature count. |
| Food quality / procurement | AgNext applies AI/spectral/image workflows at procurement points. | Field health and market-quality instruments are separate products with different validation and buyer incentives. |
| Farmer service platform | DeHaat operates a large assisted-service/input/market network. | Tier 0–3 adoption needs trusted local channels; keep marketplace incentives separated from advice. |
| Industrial LPWAN | SenseCAP provides battery LoRaWAN soil/weather nodes, gateway and API. | Private LoRa is viable only with radio survey, gateway O&M and regional approval; not a universal connectivity claim. |

### AgriTech-unicorn check

Valuation is neither a hardware-readiness metric nor stable engineering evidence. A January 2026 Indian-sector report states the Indian agritech segment had not produced a unicorn at that time, despite heavily funded companies; later media claims conflict. AgriGrow will track **service revenue, calibrated active assets, repair turnaround and measured farmer value**, not unicorn status, as investment readiness criteria. [Entrackr report](https://entrackr.com/files/entrackr/media/files/2026/01/29/agritech-report-2026-01-29-01-38-33.pdf)

## 4. Research-paper survey and implications

| Paper / source | Finding relevant to AgriGrow | Architectural consequence |
|---|---|---|
| [Mane et al., 2024, dielectric moisture calibration review](https://www.sciencedirect.com/science/article/pii/S0168169924000772) | Sensor/soil/environment-specific calibration is central to usable dielectric moisture data. | No universal VWC claim; maintain soil/crop calibration profiles and field gravimetric programme. |
| [Advanced soil-moisture monitoring review, 2024](https://www.sciencedirect.com/science/article/pii/S2666154324005106) | Sensor depth, modality and remote/on-the-go integration create different strengths and errors. | Store depth, installation and method; combine sources only through declared model contracts. |
| [IoT and AI smart-sensing systematic review](https://pmc.ncbi.nlm.nih.gov/articles/PMC12196926/) | Literature identifies infrastructure cost, interoperability, rural connectivity, transparency and privacy as recurring barriers. | Offline-first, open schema, tier-aware quality and consent are product requirements, not later features. |
| [On-site soil and plant sensor review](https://www.mdpi.com/2077-0472/16/8/883) | Paper/printed electrochemical and handheld optical tools have promise but need applied validation. | Tier 0 and future spectral tools are screening/research until their reference-method validation passes. |
| [Plant-sensor adoption review](https://www.nature.com/articles/s44287-024-00131-9) | Field deployability and species generalisation remain core barriers to plant sensing. | Treat leaf/plant wearable sensing as research-stage, not S1 feature. |
| [Ground/air/space sensor-fusion review](https://www.mdpi.com/2073-4395/13/7/1942) | Proximal and remote sensing are complementary rather than substitutes. | Use satellite/drone as contextual layer; never overwrite a ground measurement. |
| [Nutrient-sensing review](https://www.mdpi.com/1424-8220/25/2/453) | Standardisation, integration and calibration barriers persist for open-field nutrient sensing. | Direct field N/P/K remains research-stage unless a crop/soil assay is independently validated. |
| [Ambient-IoT precision agriculture review](https://arxiv.org/abs/2409.12281) | Energy-harvesting sensor networks are promising but constraints remain. | Energy-harvesting is research/pilot; Tier 4 uses conservative solar/battery design today. |

## 5. Patent landscape (screening only)

| Family / public record | Relevance | AgriGrow design action |
|---|---|---|
| [US8104498B2 soil moisture sensor/controller](https://patents.google.com/patent/US8104498B2/en) | Integrates capacitance moisture sensing with irrigation interruption/control. | Keep AgriGrow sensor telemetry separate from local controller and obtain FTO counsel before Tier 5 designs. |
| [AU2021100323 IoT irrigation](https://patents.google.com/patent/AU2021100323A4/en) | Sensor, processing, relay, cloud/GUI irrigation concept. | Generic architecture is crowded; do not pursue broad “IoT irrigation” claims. |
| [WO2023118326 targeted weed control](https://patents.google.com/patent/WO2023118326A1/en) | Image-based weed/crop classification and selective spraying claims. | Camera-assisted actuation has dense claim space; use a specialist FTO review before any product claim. |
| [US20240260563 image-per-nozzle spraying](https://patents.google.com/patent/US20240260563A1/en) | Camera/nozzle association for selective spray. | Avoid copying mapping/control architecture; focus present IP on provenance/calibration/service. |
| [WO2025120407 predictive IoT irrigation](https://patents.google.com/patent/WO2025120407A1/en) | Soil/weather based prediction/control. | Monitor prosecution/status; a publication is not clearance or validity analysis. |
| [WIPO agrifood landscape](https://www.wipo.int/web-publications/patent-landscape-report-agrifood/assets/67335/2010%20Patent%20Landscape%20Report%20-%20Agrifood_WEB.pdf) | Shows breadth of agrifood IP landscape. | Commission jurisdiction-, claim- and status-specific legal search before disclosure, manufacture or sale. |

## 6. Open-source and public building blocks

| Project | Useful element | Use / avoid |
|---|---|---|
| [FarmBot](https://farm.bot/pages/open-source) | Published CAD, BOM, software and tool-interface approach | Use as repairability/open-interface reference; not a broad-acre/weatherproof product baseline. |
| [AgOpenGPS](https://docs.agopengps.com/) | Community GPS guidance, section control, hardware/firmware documentation | Evaluate integration adapter and licence/version; do not carry its machine-control risk into farmer handhelds. |
| [ChirpStack](https://www.chirpstack.io/) | Open-source multi-tenant LoRaWAN server with REST/gRPC/MQTT integration | Candidate for controlled Tier 5 private networks; requires security hardening, operations and Indian regional plan. |
| [ENTS](https://jlab-sensing.github.io/ENTS/) | Open environmental sensing architecture | Research/reference implementation, not certification-ready product. |
| Arduino/ESP32 ecosystem | Fast prototype components and libraries | Use only in early EVT or non-safety tools; production requires secure lifecycle, RF/compliance and supply assurance. |

## 7. Indian public-infrastructure alignment

| Initiative / institution | Relevance | AgriGrow action |
|---|---|---|
| [Soil Health Card scheme](https://soilhealth.dac.gov.in/files/FAQ_Final_English.pdf) | Defines lab-tested nutrient/physical-parameter context and sample practice. | Tier 0–3 capture protocol/sample chain; never present a consumer probe as a replacement for the accredited/lab pathway. |
| [ICAR KVK network](https://icar.gov.in/en/agricultural-extension-division) | KVKs conduct assessment, demonstrations, capacity building and advisory support. | Use KVKs as Tier 0/3 pilots, training, calibration and independent field-validation partners. |
| [STPI FASAL CoE](https://fasal.stpi.in/) | Government-supported IoT-in-agriculture incubation and laboratory ecosystem. | Explore test, incubation and deployment collaboration—not assumed procurement access. |
| [BIS notified products](https://www.bis.gov.in/product-certification/products-under-compulsory-certification/?lang=en) / [TEC IoT](https://www.tec.gov.in/internet-of-things-iot) | Compliance status is product/radio-configuration specific. | Maintain living SKU matrix; validate WPC/ETA, TEC/MTCTE/BIS and battery/EMC/IP obligations before PVT. |
| SHC sampling guidance | Specifies trained collection, depth and multi-point mixing context. | Put sample protocol in app/device and attach protocol deviations to every comparable soil result. |

## 8. What AgriGrow should improve—and avoid

| Improve deliberately | Avoid explicitly |
|---|---|
| A single event/provenance contract from manual kit to research station | Treating many cheap readings as an accuracy substitute |
| Low-cost shared/assisted entry with KVK/FPO service | Consumer “instant NPK/soil health” claims without independent assay validation |
| Replaceable probes, calibration logistics and technician diagnostics | Sealing every component into an unrepairable unit |
| Offline-first, multilingual, explanation-led farmer workflow | Dashboard-first adoption assumptions or hidden subscription/marketplace steering |
| Independent safety controller and human override for Tier 5 actuation | Cloud/LLM direct control of pumps, valves, fertiliser or pesticide application |
| Interoperable professional interfaces and documented adapters | Locking farmers into a proprietary sensor/data silo |
| Federated public-interest aggregates with consent/purpose controls | A national raw-data lake that exposes individual farm/location data |

