# Lock Witness — Atomic Feature Audit, Part 2

**Continuation of [Part 1](FEATURE-MATRIX.md), items 1–152.** Evidence snapshot: private source main commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e` and verified official Google Play listing (July 22, 2026 update).

Legend: **B** = a competitor publicly advertises the broad related feature category (not identical behavior), **?** = no verified detailed parity. L=Lockwatch, C=CrookCatcher, T=Third Eye, W=WTMP (Mindfulness Devs), P=Prey. See [METHODOLOGY.md](METHODOLOGY.md) for direct primary sources. A row marked **Not implemented** or **Not verified** is explicitly **not marketed as a shipped capability**.

## Local evidence packaging and export (24)

**Source:** `android/app/src/main/java/com/lockwitness/app/export/LocalIncidentExporter.kt`, `android/app/src/main/java/com/lockwitness/app/export/IncidentExportFormatter.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/ExportEvidenceScreen.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 153 | Generate ZIP archive | Code / recorded evidence | ? | ? | ? | ? | ? |
| 154 | Write metadata.json entry | Code / recorded evidence | ? | ? | ? | ? | ? |
| 155 | Write incidents.csv entry | Code / recorded evidence | ? | ? | ? | ? | ? |
| 156 | Write hashes.txt entry | Code / recorded evidence | ? | ? | ? | ? | ? |
| 157 | Include captured JPEGs | Code / recorded evidence | B | B | B | B | ? |
| 158 | Include captured MP4s | Code / recorded evidence | B | B | B | B | ? |
| 159 | Use photos/ archive folder | Code / recorded evidence | B | B | B | B | ? |
| 160 | Use videos/ archive folder | Code / recorded evidence | B | B | B | B | ? |
| 161 | Use system timestamp in export filename | Code / recorded evidence | ? | ? | ? | ? | ? |
| 162 | Record exported incident count | Code / recorded evidence | ? | ? | ? | ? | ? |
| 163 | Record included media count | Code / recorded evidence | ? | ? | ? | ? | ? |
| 164 | Identify files missing at export time | Code / recorded evidence | ? | ? | ? | ? | ? |
| 165 | List missing media in JSON | Code / recorded evidence | ? | ? | ? | ? | ? |
| 166 | List missing media in hash manifest | Code / recorded evidence | ? | ? | ? | ? | ? |
| 167 | Write escaped CSV fields | Code / recorded evidence | ? | ? | ? | ? | ? |
| 168 | Write JSON-escaped metadata | Code / recorded evidence | ? | ? | ? | ? | ? |
| 169 | Record 21-column incident CSV structure | Code / recorded evidence | ? | ? | ? | ? | ? |
| 170 | Expose exporting progress UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 171 | Expose export success UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 172 | Expose export failure UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 173 | Offer Share/Save after export | Code / recorded evidence | ? | ? | ? | ? | ? |
| 174 | Allow export from incident detail | Code / recorded evidence | B | B | B | B | ? |
| 175 | Keep ZIP in app-private exports directory | Code / recorded evidence | ? | ? | ? | ? | ? |
| 176 | No certified PDF evidence report (not implemented) | Not implemented | ? | ? | ? | ? | ? |

## Manual sharing and alerts (15)

**Source:** `android/app/src/main/java/com/lockwitness/app/ui/screens/ShareEvidenceScreen.kt`, `android/app/src/main/java/com/lockwitness/app/alert/AlertIncidentUpdater.kt`, `android/app/src/main/java/com/lockwitness/app/alert/AlertShareIntentBuilder.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 177 | Offer Android ACTION_SEND flow | Code / recorded evidence | ? | ? | ? | ? | ? |
| 178 | Use application/zip MIME type | Code / recorded evidence | ? | ? | ? | ? | ? |
| 179 | Share FileProvider content URI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 180 | Use FLAG_GRANT_READ_URI_PERMISSION | Code / recorded evidence | ? | ? | ? | ? | ? |
| 181 | Open Android chooser | Code / recorded evidence | ? | ? | ? | ? | ? |
| 182 | Require user-selected destination | Code / recorded evidence | ? | ? | ? | ? | ? |
| 183 | Never silently upload ZIP | Code / recorded evidence | ? | ? | ? | ? | ? |
| 184 | Allow share/email setting | Code / recorded evidence | ? | ? | ? | ? | ? |
| 185 | Record user-action-required alert state | Code / recorded evidence | ? | ? | ? | ? | ? |
| 186 | Record manual share action launched | Code / recorded evidence | ? | ? | ? | ? | ? |
| 187 | Record manual share failure | Code / recorded evidence | ? | ? | ? | ? | ? |
| 188 | Keep share history in incident Room record | Code / recorded evidence | ? | ? | ? | ? | ? |
| 189 | Disclose privacy sensitivity before sharing | Code / recorded evidence | ? | ? | ? | ? | ? |
| 190 | No automatic email alert delivery (not implemented) | Not implemented | ? | ? | ? | ? | ? |
| 191 | No continuous remote alert retry (not implemented) | Not implemented | ? | ? | ? | B | B |

## Persistent preferences and settings (24)

**Source:** `android/app/src/main/java/com/lockwitness/app/data/SettingsRepository.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/SettingsScreen.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 192 | Use DataStore Preferences | Code / recorded evidence | ? | ? | ? | ? | ? |
| 193 | Persist master monitoring toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 194 | Persist photo toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 195 | Persist video toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 196 | Persist location toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 197 | Persist local timeline toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 198 | Persist email-alert toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 199 | Persist share-alert toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 200 | Persist evidence-hashing toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 201 | Persist auto-delete-days choice | Code / recorded evidence | ? | ? | ? | ? | ? |
| 202 | Support zero retention timeout selection | Code / recorded evidence | ? | ? | ? | ? | ? |
| 203 | Support 30-day retention choice | Code / recorded evidence | ? | ? | ? | ? | ? |
| 204 | Support 60-day retention choice | Code / recorded evidence | ? | ? | ? | ? | ? |
| 205 | Support 90-day retention choice | Code / recorded evidence | ? | ? | ? | ? | ? |
| 206 | Support 5/10/15/30-second video duration | Code / recorded evidence | B | B | B | B | ? |
| 207 | Validate unsupported video duration | Code / recorded evidence | B | B | B | B | ? |
| 208 | Request CAMERA permission from settings | Code / recorded evidence | ? | ? | ? | ? | ? |
| 209 | Request LOCATION permission from settings | Code / recorded evidence | ? | ? | ? | ? | ? |
| 210 | Show Device Admin active state | Code / recorded evidence | B | B | B | B | ? |
| 211 | Open Device Admin activation | Code / recorded evidence | B | B | B | B | ? |
| 212 | Show Pro feature badges | Code / recorded evidence | ? | ? | ? | ? | ? |
| 213 | Show storage information | Code / recorded evidence | ? | ? | ? | ? | ? |
| 214 | Show manual clear/delete action | Code / recorded evidence | ? | ? | ? | ? | ? |
| 215 | Automated retention purge for saved days (not verified) | Not verified | ? | ? | ? | ? | ? |

## Dashboard, onboarding and navigation (22)

**Source:** `android/app/src/main/java/com/lockwitness/app/ui/screens/DashboardScreen.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/SetupScreen.kt`, `android/app/src/main/java/com/lockwitness/app/ui/LockWitnessApp.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 216 | Compose/Material 3 dashboard | Code / recorded evidence | ? | ? | ? | ? | ? |
| 217 | Show monitoring active versus paused | Code / recorded evidence | B | B | B | B | ? |
| 218 | Show recent incident timestamp | Code / recorded evidence | B | B | B | B | ? |
| 219 | Show total incident count | Code / recorded evidence | B | B | B | B | ? |
| 220 | Show captured-photo count | Code / recorded evidence | B | B | B | B | ? |
| 221 | Show captured-video count | Code / recorded evidence | B | B | B | B | ? |
| 222 | Show capture-module status tiles | Code / recorded evidence | ? | ? | ? | ? | ? |
| 223 | Show photo/video/location/export module cards | Code / recorded evidence | B | B | B | B | ? |
| 224 | Show evidence-hashing status indicator | Code / recorded evidence | ? | ? | ? | ? | ? |
| 225 | Show current trial/Pro status | Code / recorded evidence | ? | ? | ? | ? | ? |
| 226 | Show trial countdown when active | Code / recorded evidence | ? | ? | ? | ? | ? |
| 227 | Show upgrade navigation | Code / recorded evidence | ? | ? | ? | ? | ? |
| 228 | Show Setup wizard | Code / recorded evidence | ? | ? | ? | ? | ? |
| 229 | Explain Device Admin authorization | Code / recorded evidence | B | B | B | B | ? |
| 230 | Request camera permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 231 | Request location permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 232 | Show onboarding completion status | Code / recorded evidence | ? | ? | ? | ? | ? |
| 233 | Navigate dashboard/history/settings/diagnostics/about | Code / recorded evidence | ? | ? | ? | ? | ? |
| 234 | Open incident detail from history | Code / recorded evidence | B | B | B | B | ? |
| 235 | Open export screen | Code / recorded evidence | ? | ? | ? | ? | ? |
| 236 | Open share screen | Code / recorded evidence | ? | ? | ? | ? | ? |
| 237 | Provide light/dark visual styles through Compose theme | Code / recorded evidence | ? | ? | ? | ? | ? |

## Diagnostics, verification and failure handling (20)

**Source:** `android/app/src/main/java/com/lockwitness/app/diagnostics/DiagnosticModels.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/DiagnosticsScreen.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 238 | Map runtime diagnostic checks | Code / recorded evidence | ? | ? | ? | ? | ? |
| 239 | Check Device Admin activation | Code / recorded evidence | B | B | B | B | ? |
| 240 | Check master monitoring setting | Code / recorded evidence | B | B | B | B | ? |
| 241 | Check camera permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 242 | Check location permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 243 | Check photo toggle | Code / recorded evidence | ? | ? | ? | ? | ? |
| 244 | Check video toggle and plan | Code / recorded evidence | ? | ? | ? | ? | ? |
| 245 | Check location toggle and plan | Code / recorded evidence | ? | ? | ? | ? | ? |
| 246 | Check local timeline availability | Code / recorded evidence | ? | ? | ? | ? | ? |
| 247 | Check evidence/export availability | Code / recorded evidence | ? | ? | ? | ? | ? |
| 248 | Show pass/fail/unavailable status | Code / recorded evidence | ? | ? | ? | ? | ? |
| 249 | Offer photo capture test | Code / recorded evidence | B | B | B | B | ? |
| 250 | Offer video capture test | Code / recorded evidence | B | B | B | B | ? |
| 251 | Offer location snapshot test | Code / recorded evidence | B | B | B | B | ? |
| 252 | Offer local ZIP export test | Code / recorded evidence | ? | ? | ? | ? | ? |
| 253 | Report diagnostic action failures | Code / recorded evidence | ? | ? | ? | ? | ? |
| 254 | Show missing permission state | Code / recorded evidence | ? | ? | ? | ? | ? |
| 255 | Use diagnostic placeholder incident when empty | Code / recorded evidence | ? | ? | ? | ? | ? |
| 256 | Keep diagnostic placeholder out of incident history | Code / recorded evidence | ? | ? | ? | ? | ? |
| 257 | Disclose Pro-locked diagnostics | Code / recorded evidence | ? | ? | ? | ? | ? |

## Monetization, billing, plans and trial (30)

**Source:** `android/app/src/main/java/com/lockwitness/app/monetization/MonetizationModels.kt`, `android/app/src/main/java/com/lockwitness/app/monetization/MonetizationRepository.kt`, `android/app/src/main/java/com/lockwitness/app/monetization/PlayBillingService.kt`, `android/app/src/main/java/com/lockwitness/app/monetization/ProFeatureGate.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/UpgradeScreen.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 258 | Offer monthly plan in UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 259 | Offer annual plan in UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 260 | Offer lifetime plan in UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 261 | Use Google Play Billing 9.1.0 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 262 | Query subscription SKUs | Code / recorded evidence | ? | ? | ? | ? | ? |
| 263 | Query lifetime in-app SKU | Code / recorded evidence | ? | ? | ? | ? | ? |
| 264 | Launch Play Billing flow | Code / recorded evidence | ? | ? | ? | ? | ? |
| 265 | Consume purchase-updated callback | Code / recorded evidence | ? | ? | ? | ? | ? |
| 266 | Acknowledge purchased item | Code / recorded evidence | ? | ? | ? | ? | ? |
| 267 | Requery existing subscriptions | Code / recorded evidence | ? | ? | ? | ? | ? |
| 268 | Requery lifetime purchase | Code / recorded evidence | ? | ? | ? | ? | ? |
| 269 | Display Pro state | Code / recorded evidence | ? | ? | ? | ? | ? |
| 270 | Display billing unavailable state | Code / recorded evidence | ? | ? | ? | ? | ? |
| 271 | Persist trial start time | Code / recorded evidence | ? | ? | ? | ? | ? |
| 272 | Calculate remaining trial days | Code / recorded evidence | ? | ? | ? | ? | ? |
| 273 | Mark trial expiration | Code / recorded evidence | ? | ? | ? | ? | ? |
| 274 | Grant Pro feature gates during trial | Code / recorded evidence | ? | ? | ? | ? | ? |
| 275 | Gate video after trial for non-Pro | Code / recorded evidence | ? | ? | ? | ? | ? |
| 276 | Gate GPS after trial for non-Pro | Code / recorded evidence | ? | ? | ? | ? | ? |
| 277 | Gate full history after trial | Code / recorded evidence | ? | ? | ? | ? | ? |
| 278 | Gate ZIP in ProFeatureGate helper | Code / recorded evidence | ? | ? | ? | ? | ? |
| 279 | Fallback to free entitlement on billing unavailability | Code / recorded evidence | ? | ? | ? | ? | ? |
| 280 | Advertise $2.99 monthly on Play | Code / recorded evidence | ? | ? | ? | ? | ? |
| 281 | Advertise $19.99 annual on Play | Code / recorded evidence | ? | ? | ? | ? | ? |
| 282 | Advertise $39.99 lifetime on Play | Code / recorded evidence | ? | ? | ? | ? | ? |
| 283 | Independent Play purchase verification (not verified) | Not verified | ? | ? | ? | ? | ? |
| 284 | Server-side purchase receipt verification (not implemented) | Not implemented | ? | ? | ? | ? | ? |
| 285 | Reinstall-resistant trial identity (not implemented) | Not implemented | ? | ? | ? | ? | ? |
| 286 | Consistency of trial/free-tier marketing (not verified) | Not verified | ? | ? | ? | ? | ? |
| 287 | End-to-end export paywall enforcement (not verified) | Not verified | ? | ? | ? | ? | ? |

## Privacy, permissions and device-owner controls (25)

**Source:** `android/app/src/main/AndroidManifest.xml`, `android/app/src/main/java/com/lockwitness/app/ui/screens/AboutScreen.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/SetupScreen.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/ShareEvidenceScreen.kt`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 288 | Device-owner initiated monitoring setup | Code / recorded evidence | B | B | B | B | ? |
| 289 | No automatic network upload in manifest | Code / recorded evidence | ? | ? | ? | ? | ? |
| 290 | No INTERNET permission in manifest | Code / recorded evidence | ? | ? | ? | ? | ? |
| 291 | No microphone permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 292 | No SMS permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 293 | No contacts permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 294 | No AccessibilityService in application | Code / recorded evidence | ? | ? | ? | ? | ? |
| 295 | No overlay permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 296 | No call-log permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 297 | No hidden app-icon mechanism | Code / recorded evidence | ? | ? | ? | ? | ? |
| 298 | No anti-uninstall hardening | Code / recorded evidence | ? | ? | ? | ? | ? |
| 299 | Store photos/videos in app-private files | Code / recorded evidence | B | B | B | B | ? |
| 300 | Disable Android backup in manifest | Code / recorded evidence | ? | ? | ? | ? | ? |
| 301 | Only foreground-service camera capture | Code / recorded evidence | ? | ? | ? | ? | ? |
| 302 | Show foreground-service notification | Code / recorded evidence | ? | ? | ? | ? | ? |
| 303 | Require Device Admin disclosure | Code / recorded evidence | B | B | B | B | ? |
| 304 | Explain camera permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 305 | Explain location permission | Code / recorded evidence | ? | ? | ? | ? | ? |
| 306 | Allow independent media toggles | Code / recorded evidence | ? | ? | ? | ? | ? |
| 307 | Disclose GPS and faces before sharing | Code / recorded evidence | ? | ? | ? | ? | ? |
| 308 | Only manual Android chooser for transfer | Code / recorded evidence | ? | ? | ? | ? | ? |
| 309 | Do not claim biometric failure detection | Code / recorded evidence | ? | ? | ? | ? | ? |
| 310 | No cloud account/login requirement | Code / recorded evidence | ? | ? | ? | ? | ? |
| 311 | No remote device locator (not implemented) | Not implemented | ? | ? | ? | B | B |
| 312 | No forced remote wipe (not implemented) | Not implemented | ? | ? | ? | B | B |

## Testing, Android compliance and release evidence (24)

**Source:** `android/app/build.gradle.kts`, `android/app/src/test/java/com/lockwitness/app`, `docs/PHASE_19_REPORT.md`, `README.md`, `PROJECT_STATE.md`.

| # | Individual behavior or documented gap | Lock Witness evidence | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 313 | Android minimum API 26 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 314 | Compile Android API 36 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 315 | Target Android API 36 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 316 | Application version 1.0.4 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 317 | versionCode 5 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 318 | Jetpack Compose UI | Code / recorded evidence | ? | ? | ? | ? | ? |
| 319 | Kotlin 2.3.10 source toolchain | Code / recorded evidence | ? | ? | ? | ? | ? |
| 320 | Gradle 8.13 wrapper | Code / recorded evidence | ? | ? | ? | ? | ? |
| 321 | AGP 8.11.0 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 322 | Room 2.8.4 persistence | Code / recorded evidence | ? | ? | ? | ? | ? |
| 323 | Google Play Billing 9.1.0 | Code / recorded evidence | ? | ? | ? | ? | ? |
| 324 | R8 minification for release | Code / recorded evidence | ? | ? | ? | ? | ? |
| 325 | Release resource shrink | Code / recorded evidence | ? | ? | ? | ? | ? |
| 326 | Keystore from non-versioned properties | Code / recorded evidence | ? | ? | ? | ? | ? |
| 327 | 57 unit tests in Phase 19 report | Code / recorded evidence | ? | ? | ? | ? | ? |
| 328 | Core photo tested on Android 12 hardware | Code / recorded evidence | ? | ? | ? | ? | ? |
| 329 | Video tested on Android 12 hardware | Code / recorded evidence | ? | ? | ? | ? | ? |
| 330 | Location diagnostic tested with cached fix | Code / recorded evidence | ? | ? | ? | ? | ? |
| 331 | ZIP and SHA rehash checked on hardware | Code / recorded evidence | ? | ? | ? | ? | ? |
| 332 | Share chooser tested on hardware | Code / recorded evidence | ? | ? | ? | ? | ? |
| 333 | API-36 foreground camera service tested on emulator | Code / recorded evidence | ? | ? | ? | ? | ? |
| 334 | Physical Android 16 JPEG capture (not verified) | Not verified | ? | ? | ? | ? | ? |
| 335 | Live monthly purchase flow (not verified) | Not verified | ? | ? | ? | ? | ? |
| 336 | Independent penetration test (not verified) | Not verified | ? | ? | ? | ? | ? |

## Total and serious qualifications

**336 numbered source-mapped entries across both matrices.** Some entries are explicit absence or unverified status, so the total is a traceability count, **not a count of shipped features**. Code presence is distinct from historical physical-device testing and a new live-purchase validation.

**Important commercial gap:** current code enables Pro features during the seven-day trial, but repository marketing and older checklists disagree about the trial's scope and permanent free access. The local exporter is not itself a billing-enforcing component; a billing helper gate is not proof of every UI entry-point guard. See [MONETIZATION-AUDIT.md](MONETIZATION-AUDIT.md).

**Important integrity limit:** SHA-256 can show that a file changed compared with a previously recorded hash; it cannot prove who held the device, original capture time under a trusted clock, admissibility or that a malicious actor never altered both file and manifest. [Evidence details](EVIDENCE-INTEGRITY.md).

[Portofolio home](README.md) · [Competitor comparison](COMPARISON.md).