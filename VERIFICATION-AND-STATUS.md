# Lock Witness — Current Release and Verification Status

**Source:** `Amishgangsta/LockWitness` main commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`, latest recorded source commit July 22, 2026. **Independent public source:** [Google Play listing for Lock Witness](https://play.google.com/store/apps/details?id=com.lockwitness.app), inspected November 13, 2026.

## Verified release facts

| Dimension | Source-verified status | Evidence |
|---|---|---|
| Official product spelling | **Lock Witness** | Google Play display name |
| App package | `com.lockwitness.app` | Play app URL, Android Gradle `applicationId` |
| Store publication | **Listed and installable** at time of web check | Google Play product page |
| Published app release | v1.0.4 / versionCode 5 | Gradle configuration; Play updated July 22, 2026 |
| Compile and target | Android API 36 / Android 16 | `android/app/build.gradle.kts` |
| Billing dependency | Google Play Billing 9.1.0 | Gradle catalog and July 22 report |
| Last recorded unit-test run | **57 tests, zero failures** | Phase 19 report/README dated July 22 |
| GitHub Actions | **Successful** on inspected main commit | GitHub Actions API |
| Device Admin wrong-unlock callback | **Physical device verified** | Phase 14-C recorded Android 12 Samsung test |
| Front-camera JPEG and SHA-256 | **Physical device verified** | Phase 14-D and 14-F evidence |
| Silent MP4 recording | **Physical device verified** | Phase 14-H and Phase 18 reports |
| Last-known location snapshot | **Physical-device diagnostic verified** | Warm-cache test, not a guaranteed instant fix |
| ZIP archive with hash verification | **Physical device verified** | Phase 14-F report, 41-MB ZIP, 13 matching media hashes |
| Manual share chooser | **Physical device verified** | Phase 14-G |
| Android 16 locked-screen camera FGS | **Emulator invocation verified** | Phase 19 API-36 emulator tests |
| Android 16 real JPEG output | **Not verified on target 36 physical device** | Emulator camera did not provide a successful JPEG |
| Real Google Play purchase and restore | **Not verified from available current sources** | Source code exists; no Play Console execution evidence |
| Third-party forensic/security certification | **Not verified** | No independent report supplied |

## Device limitations disclosed

- Android credential failure callbacks cover PIN/password/pattern, **not fingerprint or face-unlock failures**.
- Device Admin authorization, camera permissions, supported camera hardware, and foreground-service policies determine capture availability.
- The location provider returns the **latest available cached location**, and may return `UNAVAILABLE`.
- A SHA-256 fingerprint proves byte-for-byte correspondence to a trustworthy earlier fingerprint, **not identity, original capture time or court admissibility**.
- Manual sharing does not recover evidence from a missing phone unless the owner previously exported it; there is **no automatic remote backup**.

## Public marketing/product consistency findings

The Google Play description advertises a seven-day trial and three prices. The Kotlin gate gives active-trial users Pro access, while older source checklists and store-listing copy disagree on the exact trial scope and whether free functionality persists after expiry. [The separate audit](MONETIZATION-AUDIT.md) documents these source conflicts without assuming a checkout outcome.

## What was not done for this portfolio

No Android APK was freshly compiled, no new 57-test run was executed, no physical Android 16 hardware was used, no paid entitlement was purchased, no proprietary competitor APK was inspected and no independent forensic benchmark was conducted. All data comes from the current GitHub source, the existing dated verification reports and current vendor/Play pages.

[Detailed individual feature register](FEATURE-MATRIX.md) · [Evidence-format analysis](EVIDENCE-INTEGRITY.md) · [Methodology](METHODOLOGY.md)
