# WHY CHOOSE LOCK WITNESS?
## In-depth five-competitor review, feature by feature

**Reviewed November 13, 2026. Exact brand name: Lock Witness.** This report is written as a software engineering and product portfolio for future clients and employers, with separately grounded customer-facing positioning.

> **Primary distinction:** Lock Witness deliberately emphasizes *owner-controlled, on-device evidence retention* with photo/video SHA-256 fingerprints and a manually generated ZIP package containing media, CSV, JSON and a hash manifest. It is not the only Android intruder-photo app, and it is not a remotely managed phone-recovery platform.

[Live Google Play product](https://play.google.com/store/apps/details?id=com.lockwitness.app) · [Public brochure](BROCHURE.md) · [336-item source audit](FEATURE-MATRIX.md) · [Evidence-integrity explanation](EVIDENCE-INTEGRITY.md)

## Five comparators — current products, not hypothetical versions

1. **Lockwatch – Thief Catcher** (BlokeTech): failed-unlock selfies and location by automatic email; premium silent? **No — official listing says video with sound**, additional camera, SIM-change/power-on alerts.
2. **CrookCatcher: Who Touched?** (CrookCatcher): free intruder photo and location sent to the user's email, Pro video with sound, Google Drive backup, disguise/anti-shutdown functions.
3. **Third Eye – Intruder Detection** (Mirage Stacks): wrong-code selfie, detailed photo logs, last-unlock time, notifications and configuration.
4. **WTMP — Who touched my phone?** (Mindfulness Devs): background front-camera records on attempted or successful unlock, app-usage logs and optional cloud synchronization.
5. **Prey: Tracking & Security** (Prey): wider lost/stolen-device recovery solution using remote console, missing-mode photo/location reporting, remote lock/alarm and geofence functions.

## Where Lock Witness leads, ties or trails

| Purchase or engineering consideration | Lock Witness | Verified rival context | Outcome |
|---|---|---|---|
| Failed-unlock photo | Captures front-camera image | Lockwatch, CrookCatcher, Third Eye, WTMP advertise equivalent category | **Tie** |
| Photo and video evidence with per-file SHA-256 | Hashes stored, visible and included in manifest | Exact peer per-file public hash-export equivalence not established | **Documented implementation distinction, not proven exclusive** |
| Portable evidence package | On-demand ZIP with JSON/CSV/hashes/media | None of five current public pages establishes exact bundle equivalence | **Source-verified product differentiation; peer parity unknown** |
| Automatic remote notifications | No silent email/cloud upload | Lockwatch and CrookCatcher email evidence; Prey sends remote reports | **Rival advantage for recovery; Locke's opt-in privacy choice** |
| Video evidence | Front camera, silent, duration options, gated | Lockwatch and CrookCatcher advertise video with sound | **Different privacy choice; no universal lead** |
| Live location and remote recovery | Last known snapshot on event, no remote dashboard | Prey supports live device location and remote actions | **Prey leads in remote theft recovery** |
| Support and verification | Recorded Android 12 hardware tests, Android 16 emulator FGS test, 57 unit tests | Competitor internal build/test data not reviewed | **Locke evidence traceable; peer maturity not benchmarked** |
| Google Play packaging | Published plans $2.99 / $19.99 / $39.99 | Peers have free/premium models, terms vary | **Pricing positions documented; no cost lead established** |

## Complete shareable side-by-side assessment

**Legend:** **B** = published broadly comparable category, not exact parity; **?** = cannot establish a precise equivalent from official materials; **—** = a verified difference in *product architecture*, not a judgment that the other app is worse. Lock Witness statuses reflect source inspection or historical tests; a code path alone is not a new live test.

| # | Individual decision | **Lock Witness** | **Lockwatch** | **CrookCatcher** | **Third Eye** | **WTMP** | **Prey** | Interpretation |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|---|
| 1 | Detect failed PIN/password/pattern | **Implemented** | B | B | B | B | ? | Core category tie across four dedicated apps; Prey focuses theft recovery |
| 2 | Detect biometric unlock failure | **Not supported** | ? | ? | ? | ? | ? | Android failed-password callback does not expose biometrics |
| 3 | Monitor via Device Admin | **Implemented** | B | B | B | B | B | Android authorization category tie |
| 4 | Require user-granted monitoring approval | **Implemented** | B | B | B | B | B | Normal permission model; not exclusive |
| 5 | Automatic intruder selfie | **Device-tested** | B | B | B | B | B | Widely offered; no exclusive claim |
| 6 | Front-facing Camera2 implementation | **Source-verified** | ? | ? | ? | ? | ? | Competitor internals not inspected |
| 7 | Silent front-camera video | **Device-tested / Pro** | B | B | ? | ? | ? | Lockwatch and CrookCatcher advertise video with sound |
| 8 | Video clip length selector | **Code: 5/10/15/30 seconds** | ? | ? | ? | ? | ? | Exact length choices unverified for rivals |
| 9 | No microphone permission | **Source-verified** | ? | ? | ? | ? | ? | Deliberate privacy boundary; video has no audio |
| 10 | Video on failed unlock in foreground service | **Source-verified** | B | B | ? | ? | ? | Outcome category present; exact Android FGS internals unknown |
| 11 | Video capture failure status | **Source-verified** | ? | ? | ? | ? | ? | Implementation-level failure evidence |
| 12 | Location coordinate snapshot | **Device-tested / Pro** | B | B | ? | ? | B | Location tracking category tie; modes vary |
| 13 | Location's accuracy/provider recorded | **Source-verified** | ? | ? | ? | ? | ? | Data fields documented in Locke source |
| 14 | Latest-known-location behavior | **Source-verified** | ? | ? | ? | ? | ? | No guaranteed fresh GPS fix |
| 15 | No continuous remote tracking | **Architectural limitation** | B | B | ? | ? | B | Competitors offer remote/cloud mechanisms |
| 16 | Incident time and failed-attempt count | **Source-verified** | B | B | B | B | B | Basic incident evidence tie |
| 17 | Local incident history | **Source-verified** | B | B | B | B | B | Category tie |
| 18 | Full media status per incident | **Source-verified** | ? | ? | ? | ? | ? | Source-level traceability; peer exact detail unknown |
| 19 | Device OS/model/app metadata | **Source-verified** | ? | ? | ? | ? | ? | Source-level traceability |
| 20 | SHA-256 photo hash saved | **Device-tested** | ? | ? | ? | ? | ? | Defensible technical differentiator; others may also hash |
| 21 | SHA-256 video hash saved | **Source-verified** | ? | ? | ? | ? | ? | No external forensic validation claimed |
| 22 | Hash shown in incident details | **Source-verified** | ? | ? | ? | ? | ? | Evidence inspection feature |
| 23 | User-generated ZIP evidence archive | **Device-tested** | ? | ? | ? | ? | ? | Not established in published competitor material |
| 24 | CSV incident manifest | **Source-verified** | ? | ? | ? | ? | ? | Detailed export format |
| 25 | JSON incident manifest | **Source-verified** | ? | ? | ? | ? | ? | Machine-readable export |
| 26 | hashes.txt integrity manifest | **Device-tested** | ? | ? | ? | ? | ? | Verifiable file fingerprints; no chain-of-custody certificate |
| 27 | Photo/video files inside ZIP | **Source-verified** | ? | ? | ? | ? | ? | Portable offline archive |
| 28 | Missing media explicitly listed | **Source-verified** | ? | ? | ? | ? | ? | Honest export-completeness signal |
| 29 | On-device evidence storage | **Source-verified** | B | B | B | B | B | Competitors can also store locally; important is no automatic transfer |
| 30 | No automatic network evidence transmission | **Source-verified** | — | — | ? | — | — | Lockwatch/CrookCatcher automatically email; WTMP can cloud sync; Prey uses server |
| 31 | Automatic email evidence alerts | **Not implemented** | B | B | ? | ? | B | Competitor advantage in remote receipt |
| 32 | Automatic cloud backup | **Not implemented** | ? | B | ? | B | B | Competitors lead in optional off-device evidence |
| 33 | Explicit Android share chooser | **Device-tested** | B | ? | ? | ? | ? | Locke's transfer remains user-directed |
| 34 | Remote device location/control | **Not implemented** | ? | ? | ? | ? | B | Prey clearly leads on recovery operations |
| 35 | SIM-change alert | **Not implemented** | B | ? | ? | ? | B | Lockwatch publishes this feature |
| 36 | Power-on alert | **Not implemented** | B | ? | ? | ? | ? | Lockwatch publishes this feature |
| 37 | Remote lock / alarm | **Not implemented** | ? | ? | ? | ? | B | Prey capability, outside Locke's stated scope |
| 38 | App hiding / disguised icon | **Intentionally absent** | ? | B | ? | ? | ? | CrookCatcher Pro advertises disguise |
| 39 | Anti-uninstall protection | **Intentionally absent** | ? | ? | ? | B | B | WTMP uses Device Admin to block uninstall; Prey has admin controls |
| 40 | Local settings persist across relaunch | **Device-tested** | ? | ? | ? | ? | ? | Specific Locke verification evidence |
| 41 | Photo, video and GPS independently toggled | **Source-verified** | B | B | ? | ? | ? | Other apps have customization; exact per-toggle parity unverified |
| 42 | User-selectable auto-delete schedule | **UI/config present** | ? | ? | ? | ? | ? | Automated purge not separately verified |
| 43 | Diagnostics and manual capture tests | **Device-tested** | ? | ? | ? | ? | ? | Strong practical troubleshooting implementation |
| 44 | Android 16 API target | **Build-verified** | ? | ? | ? | ? | ? | Release engineering, not consumer superiority |
| 45 | Android 16 locked FGS on emulator | **Emulator-tested** | ? | ? | ? | ? | ? | Does not prove actual photo on every Android 16 device |
| 46 | 7-day trial | **Store advertised** | ? | B | ? | ? | ? | Trial behavior/copy reconciliation required |
| 47 | Published monthly plan | **$2.99** | ? | ? | ? | ? | ? | Price published; live Play purchase not independently tested |
| 48 | Published annual plan | **$19.99** | ? | ? | ? | ? | ? | Price published; no rival price ranking |
| 49 | Published lifetime offer | **$39.99** | ? | ? | ? | ? | ? | Price published; receipt test unverified |
| 50 | Lifetime Google Billing purchase query | **Source-verified** | ? | ? | ? | ? | ? | Play Console account status not inspected |
| 51 | One-time owner-triggered export | **Source-verified** | ? | ? | ? | ? | ? | Human-controlled action; exact peer parity unknown |
| 52 | Independent evidence admissibility | **Not certified** | ? | ? | ? | ? | ? | Hashes are not a legal admissibility certification |

## The most persuasive client/employer story

**Capture pipeline:** Android Device Admin receives an unlock failure, starts the camera foreground service, creates a persistent incident record, and attempts photo, video and location capture with separately recorded success/failure states.

**Integrity pipeline:** the product computes media SHA-256 hashes, stores them alongside each incident, and builds a verifiable local ZIP with manifest and source files. This lets a recipient compare media against originally recorded hash values—without claiming that the hash alone proves timing or identity.

**Control pipeline:** media modules are independently configurable; files are kept app-private; sharing opens the Android chooser. No secret upload to a remote server is advertised or visible in the manifest.

**Commercial and release engineering:** a native Compose UI, Room/DataStore persistence, Google Play Billing, 57 recorded unit tests, Android 16 target build and physical-camera verification demonstrate multi-disciplinary app work. The billing trial/copy discrepancy is disclosed rather than overlooked.

## Explicit gaps and competitor strengths

- No automatic alert emailing, remote cloud backup, remote lock/location, SIM-change warning, or fake shutdown: Lockwatch, CrookCatcher and Prey have stronger published recovery features.
- No audio on video: deliberate removal of the microphone permission, unlike competitors that advertise video with sound.
- No independently tested third-party forensic signature or court-admissibility certification.
- Location is an available last-known Android provider location, not proof of GPS coordinates measured precisely at the time of the attempted unlock.
- Current source and old marketing materials conflict about trial scope, expired-trial behavior and a long-term free tier; live subscription purchase/restore testing is not established.

## Primary sources

- **Lock Witness:** [Google Play product listing](https://play.google.com/store/apps/details?id=com.lockwitness.app); private production repository `Amishgangsta/LockWitness` at inspected commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`.
- **Lockwatch:** [Google Play](https://play.google.com/store/apps/details?id=com.bloketech.lockwatch), [developer website](https://lockwatch.app/), [official feature/limitations help](https://lockwatch.app/help).
- **CrookCatcher:** [Google Play](https://play.google.com/store/apps/details?id=com.harteg.crookcatcher), [developer website](https://www.crookcatcher.app/).
- **Third Eye:** [Google Play](https://play.google.com/store/apps/details?id=com.miragestacks.thirdeye).
- **WTMP (Mindfulness Devs):** [Google Play](https://play.google.com/store/apps/details?id=com.wtmp.svdsoftware).
- **Prey:** [Android Google Play](https://play.google.com/store/apps/details?id=com.prey), [official help](https://help.preyproject.com/article/195-how-does-prey-work), [security actions](https://support.preyproject.com/hc/en-us/articles/17224939270797-Security-actions).

No competitor APK was decompiled, no vendor private code was inspected, and no rival price or speed benchmark was performed. The 336-entry [detailed matrix](FEATURE-MATRIX.md) uses broader category-based competitor markers, not individually executed 1,680 peer-feature equivalence tests.

[Portfolio brochure](BROCHURE.md) · [Feature matrix part 1](FEATURE-MATRIX.md) · [Part 2](FEATURE-MATRIX-2.md) · [Pricing and trial audit](MONETIZATION-AUDIT.md) · [Source verification](METHODOLOGY.md)