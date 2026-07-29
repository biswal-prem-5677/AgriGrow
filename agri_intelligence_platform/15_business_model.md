# AgriGrow Business Model and Unit Economics

**Document ID:** AgriGrow-BIZ-015 | **Version:** 1.0

## 1. Value proposition

AgriGrow earns trust by helping farmers and institutions obtain better-quality field observations and use them safely. Revenue must be aligned with useful measurement, advice quality, service uptime and transparent commerce—not with maximising chemical input sales or extracting data.

## 2. Commercial model

| Customer / channel | Offer | Revenue basis | Guardrail |
|---|---|---|---|
| Farmer | Device, basic history, measurement guidance | One-time device and consumables; optional support plan | Farmer retains access to own core records without a recurring paywall. |
| FPO / NGO / extension service | Shared fleet, campaign tools, training, support | Per-device/per-operator SaaS and service contract | Named operator and member consent required. |
| Government programme | Deployment, aggregate programme analytics, service | Fixed scope and SLA, not raw-data resale | Agreement defines purpose, aggregation, retention and audit. |
| Research partner | Approved dataset/workspace and study support | Cost recovery/project fee | No unrestricted farmer-data sale. |
| Marketplace | Verified discovery/transaction service | Clearly disclosed seller fee | Commerce ranking cannot change agronomy advice. |

## 3. Unit economics framework

The preliminary base hardware COGS target in the hardware SRS is INR 8,400 at 10k units, excluding tooling, warranty reserve, logistics, certification, channel margin and tax. Treat it as a target price, not a financial forecast. Track landed COGS by part/lot, first-pass yield, rework, warranty, battery/probe replacements, provisioning/training, support tickets, data/cloud cost per active device, and collection/returns by channel.

Illustrative planning equation:

`contribution/device = realised device revenue − landed COGS − channel/fulfilment − warranty reserve − activation/training − allocated support − first-year cloud cost`

`lifetime contribution = contribution/device + service gross margin + consumable gross margin − retention/collection cost`

Model scenarios separately for farmer-owned, FPO-shared and programme-funded fleets. A shared device can raise measurement utilisation but also increases probe wear, operator identity complexity and support burden. Do not use marketplace commission to subsidise advice unless conflict controls are independently reviewed.

### Hardware portfolio affordability model

| Tier | Commercial shape | Planning price/ownership approach |
|---:|---|---|
| 0 | Consumable manual kit | INR 900–2,000 retail; KVK/FPO demonstration and replenishment make first use affordable. |
| 1 | Entry handheld | INR 4,500–8,000 retail; cooperative pool, rental or transparent capital subsidy are preferable to predatory financing. |
| 2 | Pocket Smart | INR 13,000–20,000 retail planning band, plus visible cost of probes/reference solutions and optional service. |
| 3 | Professional shared kit | INR 35,000–70,000 deployed band; lease to FPO/KVK/service provider with operator training and calibration included. |
| 4 | Installed farm tower | INR 0.9–2.0 lakh installed planning band; quote includes survey, mounting, solar, connectivity and annual O&M. |
| 5–6 | Network/research deployment | Project quotation after density, radio survey, sensor/installation and service scope; do not sell as a generic box. |
| 7–9 | Public infrastructure | Multi-year programme contract covering interoperability, data stewardship, SRE/security and independent evaluation. |

These planning bands are not subsidy promises. Any government-funded offer must publish eligible costs, service term, farmer contribution, data rights, repair responsibility and exit/ownership terms.

### Field Scout S1 volume sensitivity (planning COGS, INR/unit, ex-GST)

| Volume | 100 | 500 | 1,000 | 5,000 | 10,000 | 50,000 | 100,000 | 1,000,000 |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Expected COGS band | 20k–32k | 14k–20k | 12k–16k | 9.5k–12k | 8.4k–10.5k | 7.3k–8.8k | 6.8k–8.2k | 5.8k–7.2k |

The table includes production BOM, assembly/test and ordinary packaging assumptions; it excludes one-time NRE/tooling/certification, warranty, logistics, tax, channel margin, service and financing. Final customer price must be built from landed COGS plus those disclosed costs. A 1.6–2.2× landed-COGS planning range is plausible only after channel mix and warranty rate are evidenced; it is not an approved retail margin.

## 4. Pricing and affordability

Use transparent device + consumables pricing; consider financing/rental only with clear total cost, no data-rights exchange and a fair repair/return policy. Offer FPO/shared-kit and extension-worker configurations where a consumer-price device is unrealistic. Include buffer/reference solutions and probe care in the first-year ownership calculation; a cheap device with inaccessible calibration consumables creates false economy.

## 5. Governance metrics

Board/product reviews track farmer active value, valid measurements per deployed device, calibration compliance, advisory outcome/override, warranty, repair turnaround, NPS/trust complaint, privacy requests, aggregate-data agreements and supplier concentration. Establish a farmer/advisory ethics review for monetisation changes, targeted offers and new data partnerships.
