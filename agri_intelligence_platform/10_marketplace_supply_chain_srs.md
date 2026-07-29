# AgriGrow Marketplace and Supply Chain — System Requirements Specification

**Document ID:** AgriGrow-MKT-SRS-010 | **Version:** 1.0

## 1. Role and non-negotiables

The marketplace helps a farmer discover verified inputs, services, buyers and logistics after an advisory. It must not turn a measurement into undisclosed steering toward a seller. Recommendations and commerce are distinct screens, APIs and ranking policies; sponsored placement is labelled; no supplier may alter an agronomic conclusion.

## 2. Functional requirements

| ID | Requirement |
|---|---|
| MKT-F-001 | Maintain supplier identity, licence/certification claims, service areas, catalogue, price/stock timestamp, fulfilment terms and dispute contact. |
| MKT-F-002 | Show at least two qualifying alternatives where available and explain rank factors: distance, stock freshness, price, verified quality, delivery and farmer preference. |
| MKT-F-003 | Make advisory-to-product mapping policy-controlled; prohibited or high-risk categories require human/regulated process review. |
| MKT-F-004 | Support request-for-quote, order, invoice, delivery proof, returns and disputes as immutable state transitions. |
| MKT-F-005 | Never share a farmer's detailed measurements, identity or location with a seller absent explicit transaction-scoped permission. |
| MKT-F-006 | Keep payments with a compliant payment provider; AgriGrow stores tokens/status only, not card/UPI credentials. |

## 3. Supply-chain data model

Model `Supplier`, `LicenceEvidence`, `SKU/Service`, `Lot`, `Certificate`, `PriceOffer`, `InventorySnapshot`, `Order`, `Shipment`, `DeliveryProof`, `Return`, `Dispute` and `Recall`. Lots carry supplier-issued identifiers and evidence references; the platform labels the verification level rather than claiming laboratory assurance it does not possess. Inventory is eventually consistent and therefore shows freshness/time, with final availability confirmed at checkout.

## 4. Integrity and farmer protection

Detect suspicious price changes, duplicate sellers, forged certificates, coupon abuse, abnormal cancellation and review manipulation. Maintain recall workflow: identify affected orders/lots, stop listings, notify impacted users, record acknowledgement and retain audit trail. Prohibit dark patterns, forced bundles, harvesting unrelated data for seller leads, and financial incentives tied to a particular farmer's vulnerable status. Seller access is least privilege and cannot query farmer dashboards.

## 5. Metrics

Measure successful fulfilment, cancellation/refund, verified-lot coverage, price freshness, dispute time-to-resolution, recommendation-to-purchase separation, and farmer-reported value. Do not optimise solely for gross merchandise value or conversion when that conflicts with agronomic suitability and trust.
