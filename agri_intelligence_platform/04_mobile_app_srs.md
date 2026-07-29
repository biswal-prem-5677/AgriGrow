# AgriGrow Farmer Mobile App — System Requirements Specification

**Document ID:** AgriGrow-MOB-SRS-004 | **Version:** 1.0

## 1. Product role

The Android-first app is the farmer's identity, offline record, device gateway and explanation layer. It must remain useful on low-cost phones and intermittent 2G/3G/4G coverage. iOS is supported for institutional and family-assisted use after the Android reference flow proves usability. The handheld can complete a measurement without the app; the app makes it intelligible and synchronises it.

## 2. Primary journeys

1. **Onboard:** choose language → consent in plain language/audio → create/recover account through verified phone or assisted identity flow → add farm/field with boundary or landmark → pair device by scanning QR and confirming six-word/code challenge.
2. **Measure:** select field and task → connect device → show illustrated probe protocol → receive result/quality → capture crop stage/photo/note if desired → queue sync.
3. **Understand:** show “what we measured,” “what it may mean,” confidence, source date, recommended action, cost/effort, safety note and a “talk to expert” escalation.
4. **Manage:** view history, calibration/probe care, connection status, data permissions, export/delete requests and ownership transfer.

## 3. Functional requirements

| ID | Requirement |
|---|---|
| MOB-F-001 | Support at least Hindi, English and a remotely configurable language-pack framework; all core actions have text plus pictogram. |
| MOB-F-002 | Pair exactly one active owner relationship at a time; shared/FPO mode requires named operator session and audit trail. |
| MOB-F-003 | Keep encrypted offline queue and a local read cache; no loss on force-close, OS reboot or network change. |
| MOB-F-004 | Display measured, estimated and manually-entered values with visually distinct labels. |
| MOB-F-005 | Let user correct field/crop context without mutating an original measurement; issue a linked correction event. |
| MOB-F-006 | Offer optional voice guidance and accessible large-text mode; never send audio for cloud processing without clear action-level consent. |
| MOB-F-007 | Upload via background scheduler with Wi-Fi-only/metered-data controls, resumable multipart media, and battery-aware constraints. |

## 4. UX and accessibility requirements

Use an 8–10th-grade equivalent local-language reading target after field research, large touch targets (≥48 dp), high contrast in sun, and a capture flow requiring at most three decisions after field selection. Avoid colour-only status. The app shows calibration expiry before leaving for a field and makes “no network required for measurement” explicit. Trust is more important than engagement: notification rate defaults low, any marketing is opt-in, and advisory uncertainty is always visible.

## 5. Technical design

Native Kotlin/Jetpack Compose, Android 10+ baseline after device-fleet validation; Room/SQLCipher-equivalent encrypted local database; WorkManager for constrained sync; Bluetooth LE GATT service with versioned protobuf/CBOR messages; passkeys/OTP device-bound session support; certificate-pinned API client with rotation plan. Store device-transfer keys in Android Keystore; never treat a rooted-device attestation result as the only security control. The backend remains authoritative for consent, policy and canonical events.

The pairing protocol scans a printed factory QR containing public identity and model—not a secret. It establishes BLE Secure Connections, asks device to display a short confirmation code, then sends a server-issued, expiring ownership-binding token over the authenticated channel. A lost phone can be removed from the account web/recovery path; a lost device is marked restricted and cannot upload against the old farmer without reauthorisation.

## 6. Quality and acceptance

Test on representative low-RAM Android devices, Hindi/other language rendering, TalkBack, no-GPS/no-network, Bluetooth interference, phone clock errors, app reinstall/recovery and 10,000-event sync backlog. Release only if a farmer usability study demonstrates the PRD success criterion and accessibility review finds no blocker in account recovery, consent, result interpretation or emergency escalation.
