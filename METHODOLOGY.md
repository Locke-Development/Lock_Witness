# Lock Witness — Engineering Evidence and Competitive Research Method

**Review date:** November 13, 2026. **Public display name:** **Lock Witness**. **Source repo technical name:** `Amishgangsta/LockWitness` (the unspaced name is a GitHub identifier, not the marketing brand). **Inspected main commit:** `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`.

## Source inspection

The primary private repository contains native Kotlin code, Jetpack Compose UI, Room database, DataStore preferences, Android Device Admin receiver, Camera2 photo/video clients, Android LocationManager adapter, ZIP formatter/exporter, manual sharing UI, diagnostic checks and Play Billing logic. Key inspected files appear in each individual [feature-register section](FEATURE-MATRIX.md) and [Part 2](FEATURE-MATRIX-2.md).

Historical evidence includes `docs/PHASE_14_C_REPORT.md` through `PHASE_19_REPORT.md`, `PROJECT_STATE.md`, the July 22 README, GitHub Actions and the [live Google Play description](https://play.google.com/store/apps/details?id=com.lockwitness.app).

**No current source change was made to the private application.** Public material uses descriptions, selected app screenshots and the official app icon, rather than publishing code or real incident evidence.

## Comparator selection and official pages

| Competitor | Why it was included | Primary current verification |
|---|---|---|
| **Lockwatch – Thief Catcher** | Closest failed-unlock photo/video/location alert product | [Google Play](https://play.google.com/store/apps/details?id=com.bloketech.lockwatch); [developer site](https://lockwatch.app/); [help](https://lockwatch.app/help) |
| **CrookCatcher: Who Touched?** | Photo, location, email, video, cloud backup and app protection | [Google Play](https://play.google.com/store/apps/details?id=com.harteg.crookcatcher); [official website](https://www.crookcatcher.app/) |
| **Third Eye – Intruder Detection** | Failed-unlock selfie/history and notifications | [Google Play](https://play.google.com/store/apps/details?id=com.miragestacks.thirdeye) |
| **WTMP — Who touched my phone?** (Mindfulness Devs) | Camera log of unlock attempts and app-use records | [Google Play](https://play.google.com/store/apps/details?id=com.wtmp.svdsoftware) |
| **Prey: Tracking & Security** | Adjacent broader theft recovery, remote location and control | [Google Play](https://play.google.com/store/apps/details?id=com.prey); [official help](https://help.preyproject.com/article/195-how-does-prey-work); [security actions](https://support.preyproject.com/hc/en-us/articles/17224939270797-Security-actions) |

## Labels and verification boundaries

- **Source present:** a distinct Kotlin or Android manifest code path was inspected, without new live verification.
- **Device-tested / Emulator-tested:** dated first-party verification records specifically describe a tested outcome on identified equipment. This is historical evidence, not a new device test.
- **Not implemented / not verified:** intentional nonfeatures, active gaps or missing current proof; neither label is a customer-ready claim.
- **B (feature matrices):** competitor publicly documents a **broad similar category** such as local records, intruder selfies, video, location or history. Not exact parity with every technical sub-step.
- **? (feature matrices):** public materials do not establish exact equivalence. **It never means the competitor lacks the capability.**
- **— (comparison):** an architecture difference confirmed from public product descriptions and Locke's current source.

The 336-item inventory is an **atomic feature and evidence trace**, including negative and unresolved items. Its five-column reference matrix **is not 1,680 independently tested rival feature comparisons**. The curated 52-row comparison separates actual published competitor strengths from unverified exact detail.

## Claims that were deliberately excluded

No ranking of legal admissibility, identity accuracy, forensic completeness, attacker detection rate, capture reliability on every Android manufacturer, security against a compromised/rooted phone, revenue, ratings-based superiority, or comparable market pricing. Google Play's Data Safety responses are developer supplied. A version being on Google Play is not proof that each subscriber purchase works.

## Public/private boundary

The public repository is a software engineering and marketing showcase. It does not include proprietary application source, keystores, private tester IDs, personal user records, actual incident images, incident GPS coordinates, internal test secrets or detailed misuse instructions.

[Portfolio brochure](BROCHURE.md) · [Main comparison](COMPARISON.md) · [Status](VERIFICATION-AND-STATUS.md)
