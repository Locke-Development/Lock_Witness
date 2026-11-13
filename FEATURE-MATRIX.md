# Lock Witness — Atomic Feature Audit, Part 1

**Naming:** the published app and every public document are **Lock Witness** (two words). The private source repository is `Amishgangsta/LockWitness`, package `com.lockwitness.app`. **Source snapshot:** main commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`, November 13, 2026 review.

Every numbered entry represents a distinct feature or requirement traced to a concrete Kotlin/Android source file. **Code-present is not the same as a new successful runtime test.** Gaps are deliberately included rather than marketed as shipped.

**Competitor legend:** L=Lockwatch, C=CrookCatcher, T=Third Eye, W=WTMP (Mindfulness Devs), P=Prey. **B** means the vendor publicly advertises a broadly comparable feature category, not proof of exact implementation; **?** means detailed peer equivalence is not established. Check published vendor links and better-qualified comparisons in [COMPARISON.md](COMPARISON.md). No ? means absence.

## Android failed-unlock monitoring — 20 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/admin/LockWitnessDeviceAdminReceiver.kt`, `android/app/src/main/java/com/lockwitness/app/admin/FailedUnlockIncidentCreator.kt`, `android/app/src/main/AndroidManifest.xml`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 1 | Detect Android credential failures | Source present | ? | ? | ? | ? | ? |
| 2 | Respond to failed PIN attempt | Source present | B | B | B | B | ? |
| 3 | Respond to failed password attempt | Source present | B | B | B | B | ? |
| 4 | Respond to failed pattern attempt | Source present | B | B | B | B | ? |
| 5 | Use Device Admin watch-login policy | Source present | ? | ? | ? | ? | ? |
| 6 | Require owner activation of Device Admin | Source present | ? | ? | ? | ? | ? |
| 7 | Read failed-attempt counter when available | Source present | B | B | B | B | ? |
| 8 | Start foreground capture service from receiver | Source present | B | B | B | B | ? |
| 9 | Record FAILED_UNLOCK event code | Source present | B | B | B | B | ? |
| 10 | Record event timestamp | Source present | ? | ? | ? | ? | ? |
| 11 | Record current device model | Source present | ? | ? | ? | ? | ? |
| 12 | Record Android version | Source present | ? | ? | ? | ? | ? |
| 13 | Record application version | Source present | ? | ? | ? | ? | ? |
| 14 | Require master monitoring enabled | Source present | ? | ? | ? | ? | ? |
| 15 | Persist master monitoring state | Source present | ? | ? | ? | ? | ? |
| 16 | Allow monitoring paused state | Source present | ? | ? | ? | ? | ? |
| 17 | Keep biometric failures outside claimed coverage | Source present | ? | ? | ? | ? | ? |
| 18 | Provide explicit setup explanations | Source present | ? | ? | ? | ? | ? |
| 19 | Avoid adding device-wipe policy | Source present | ? | ? | ? | ? | ? |
| 20 | Use exported receiver permission BIND_DEVICE_ADMIN | Source present | ? | ? | ? | ? | ? |

## Foreground capture orchestration — 15 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/capture/LockWitnessCaptureService.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 21 | Use nonexported camera foreground service | Source present | B | B | B | B | ? |
| 22 | Create notification channel | Source present | ? | ? | ? | ? | ? |
| 23 | Show foreground service notification | Source present | ? | ? | ? | ? | ? |
| 24 | Pass failed count from receiver to service | Source present | B | B | B | B | ? |
| 25 | Create incident shell before media capture | Source present | B | B | B | B | ? |
| 26 | Capture photo after incident creation | Source present | B | B | B | B | ? |
| 27 | Attempt optional video capture | Source present | B | B | B | B | ? |
| 28 | Attempt optional location snapshot | Source present | B | B | B | B | ? |
| 29 | Update per-medium incident status | Source present | B | B | B | B | ? |
| 30 | Execute capture on IO coroutine | Source present | B | B | B | B | ? |
| 31 | Handle service job cancellation | Source present | ? | ? | ? | ? | ? |
| 32 | Stop foreground service on completion | Source present | ? | ? | ? | ? | ? |
| 33 | Preserve incident when media fails | Source present | B | B | B | B | ? |
| 34 | Record email/share action status without automatic upload | Source present | B | B | B | B | ? |
| 35 | Require camera foreground service permission | Source present | B | B | B | B | ? |

## Front-camera photo capture — 19 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/photo/Camera2PhotoCaptureClient.kt`, `android/app/src/main/java/com/lockwitness/app/photo/PhotoIncidentUpdater.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 36 | Use Camera2 API | Source present | B | B | B | B | ? |
| 37 | Check CAMERA runtime permission | Source present | B | B | B | B | ? |
| 38 | Find front-facing camera | Source present | B | B | B | B | ? |
| 39 | Fail when front camera unavailable | Source present | B | B | B | B | ? |
| 40 | Create app-private JPEG path | Source present | ? | ? | ? | ? | ? |
| 41 | Create camera capture session | Source present | B | B | B | B | ? |
| 42 | Capture still image with ImageReader | Source present | B | B | B | B | ? |
| 43 | Apply capture timeout | Source present | B | B | B | B | ? |
| 44 | Handle camera disconnect | Source present | B | B | B | B | ? |
| 45 | Handle camera error | Source present | B | B | B | B | ? |
| 46 | Close capture session and camera | Source present | B | B | B | B | ? |
| 47 | Release camera handler thread | Source present | B | B | B | B | ? |
| 48 | Persist successful photo path | Source present | B | B | B | B | ? |
| 49 | Calculate/store image SHA-256 | Source present | ? | ? | ? | ? | ? |
| 50 | Record SUCCESS photo status | Source present | B | B | B | B | ? |
| 51 | Record FAILED photo status | Source present | B | B | B | B | ? |
| 52 | Record DISABLED photo status | Source present | B | B | B | B | ? |
| 53 | Retain failure reason in incident notes | Source present | B | B | B | B | ? |
| 54 | Allow photo module toggle | Source present | B | B | B | B | ? |

## Front-camera video capture — 21 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/video/Camera2VideoCaptureClient.kt`, `android/app/src/main/java/com/lockwitness/app/video/VideoIncidentUpdater.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 55 | Use Camera2 for front-video recording | Source present | B | B | B | B | ? |
| 56 | Use MediaRecorder | Source present | ? | ? | ? | ? | ? |
| 57 | Require CAMERA permission | Source present | B | B | B | B | ? |
| 58 | Do not request RECORD_AUDIO permission | Source present | ? | ? | ? | ? | ? |
| 59 | Record silent MP4 | Source present | ? | ? | ? | ? | ? |
| 60 | Select supported video resolution | Source present | B | B | B | B | ? |
| 61 | Allow 5-second clip | Source present | ? | ? | ? | ? | ? |
| 62 | Allow 10-second clip | Source present | ? | ? | ? | ? | ? |
| 63 | Allow 15-second clip | Source present | ? | ? | ? | ? | ? |
| 64 | Allow 30-second clip | Source present | ? | ? | ? | ? | ? |
| 65 | Sanitize unsupported duration | Source present | ? | ? | ? | ? | ? |
| 66 | Enforce duration plus overhead timeout | Source present | ? | ? | ? | ? | ? |
| 67 | Handle camera disconnect or failure | Source present | B | B | B | B | ? |
| 68 | Release recorder and camera | Source present | B | B | B | B | ? |
| 69 | Write file in app-private directory | Source present | ? | ? | ? | ? | ? |
| 70 | Compute video SHA-256 | Source present | B | B | B | B | ? |
| 71 | Persist video path | Source present | B | B | B | B | ? |
| 72 | Record video SUCCESS | Source present | B | B | B | B | ? |
| 73 | Record video FAILED | Source present | B | B | B | B | ? |
| 74 | Record video DISABLED | Source present | B | B | B | B | ? |
| 75 | Gate video based on Pro or in-trial status | Source present | B | B | B | B | ? |

## Location snapshot capture — 17 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/location/AndroidLocationSnapshotClient.kt`, `android/app/src/main/java/com/lockwitness/app/location/LocationIncidentUpdater.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 76 | Check fine location permission | Source present | B | B | B | B | ? |
| 77 | Check coarse location permission | Source present | B | B | B | B | ? |
| 78 | Access Android LocationManager | Source present | B | B | B | B | ? |
| 79 | Use enabled GPS provider when available | Source present | B | B | B | B | ? |
| 80 | Use enabled network provider when available | Source present | ? | ? | ? | ? | ? |
| 81 | Use enabled passive provider when available | Source present | ? | ? | ? | ? | ? |
| 82 | Select newest last-known location | Source present | B | B | B | B | ? |
| 83 | Store latitude | Source present | ? | ? | ? | ? | ? |
| 84 | Store longitude | Source present | ? | ? | ? | ? | ? |
| 85 | Store accuracy when supplied | Source present | ? | ? | ? | ? | ? |
| 86 | Store location provider name | Source present | B | B | B | B | ? |
| 87 | Return UNAVAILABLE without cached fix | Source present | ? | ? | ? | ? | ? |
| 88 | Return FAILED on exception | Source present | B | B | B | B | ? |
| 89 | Return DISABLED when feature off | Source present | ? | ? | ? | ? | ? |
| 90 | Record failure reason in notes | Source present | ? | ? | ? | ? | ? |
| 91 | Gate location based on Pro/trial | Source present | B | B | B | B | ? |
| 92 | Treat snapshot as cached rather than real-time track | Source present | ? | ? | ? | ? | ? |

## Incident data persistence and history — 24 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/data/incident/SecurityIncident.kt`, `android/app/src/main/java/com/lockwitness/app/data/incident/SecurityIncidentDao.kt`, `android/app/src/main/java/com/lockwitness/app/ui/screens/HistoryScreen.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 93 | Use Room for local incident database | Source present | B | B | B | B | ? |
| 94 | Auto-generate incident ID | Source present | B | B | B | B | ? |
| 95 | Save failed-attempt count | Source present | B | B | B | B | ? |
| 96 | Save trigger type | Source present | ? | ? | ? | ? | ? |
| 97 | Save timestamp | Source present | ? | ? | ? | ? | ? |
| 98 | Save device model and OS | Source present | ? | ? | ? | ? | ? |
| 99 | Save module toggle snapshot | Source present | ? | ? | ? | ? | ? |
| 100 | Save photo and video paths | Source present | B | B | B | B | ? |
| 101 | Save coordinates and accuracy | Source present | ? | ? | ? | ? | ? |
| 102 | Save photo and video hashes | Source present | B | B | B | B | ? |
| 103 | Save per-module status | Source present | ? | ? | ? | ? | ? |
| 104 | Save incident notes | Source present | B | B | B | B | ? |
| 105 | List incidents newest first | Source present | B | B | B | B | ? |
| 106 | Open incident by ID | Source present | B | B | B | B | ? |
| 107 | Render image thumbnail when present | Source present | ? | ? | ? | ? | ? |
| 108 | Display failed-attempt history | Source present | B | B | B | B | ? |
| 109 | Display evidence status chips | Source present | ? | ? | ? | ? | ? |
| 110 | Display location-available marker | Source present | B | B | B | B | ? |
| 111 | Display shared marker | Source present | B | B | B | B | ? |
| 112 | Limit visible free history to 10 under gate | Source present | B | B | B | B | ? |
| 113 | Delete incident from history | Source present | B | B | B | B | ? |
| 114 | Expose loading state | Source present | ? | ? | ? | ? | ? |
| 115 | Expose empty state | Source present | ? | ? | ? | ? | ? |
| 116 | Expose history error state | Source present | B | B | B | B | ? |

## Incident detail and media metadata — 20 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/ui/screens/IncidentDetailScreen.kt`, `android/app/src/main/java/com/lockwitness/app/ui/history/IncidentHistoryModels.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 117 | Open selected incident detail | Source present | B | B | B | B | ? |
| 118 | Show event timestamp | Source present | ? | ? | ? | ? | ? |
| 119 | Show trigger and attempt count | Source present | ? | ? | ? | ? | ? |
| 120 | Show front-camera image | Source present | B | B | B | B | ? |
| 121 | Show photo status | Source present | B | B | B | B | ? |
| 122 | Show video status | Source present | B | B | B | B | ? |
| 123 | Show location status | Source present | B | B | B | B | ? |
| 124 | Show email status | Source present | ? | ? | ? | ? | ? |
| 125 | Show share status | Source present | B | B | B | B | ? |
| 126 | Show device information | Source present | ? | ? | ? | ? | ? |
| 127 | Show file paths | Source present | ? | ? | ? | ? | ? |
| 128 | Show image SHA-256 fingerprint | Source present | ? | ? | ? | ? | ? |
| 129 | Show video SHA-256 fingerprint | Source present | B | B | B | B | ? |
| 130 | Show notes | Source present | ? | ? | ? | ? | ? |
| 131 | Offer export navigation | Source present | ? | ? | ? | ? | ? |
| 132 | Offer delete confirmation dialog | Source present | ? | ? | ? | ? | ? |
| 133 | Delete incident record | Source present | B | B | B | B | ? |
| 134 | Show media-disabled state | Source present | ? | ? | ? | ? | ? |
| 135 | Show missing evidence state | Source present | ? | ? | ? | ? | ? |
| 136 | Display status color indicators | Source present | ? | ? | ? | ? | ? |

## Evidence integrity and metadata — 16 entries

**Code:** `android/app/src/main/java/com/lockwitness/app/photo/Sha256Hasher.kt`, `android/app/src/main/java/com/lockwitness/app/export/IncidentExportFormatter.kt`.

| # | Individual capability or gap | Lock Witness | L | C | T | W | P |
|---:|---|---|:-:|:-:|:-:|:-:|:-:|
| 137 | Compute photo SHA-256 | Source present | B | B | B | B | ? |
| 138 | Compute video SHA-256 | Source present | B | B | B | B | ? |
| 139 | Persist hash with incident record | Source present | B | B | B | B | ? |
| 140 | Display hash on detail screen | Source present | ? | ? | ? | ? | ? |
| 141 | Export hash in hashes.txt | Source present | ? | ? | ? | ? | ? |
| 142 | Export hash fields in CSV | Source present | ? | ? | ? | ? | ? |
| 143 | Export hashes in JSON | Source present | ? | ? | ? | ? | ? |
| 144 | Retain capture result status | Source present | B | B | B | B | ? |
| 145 | Preserve original capture filename | Source present | B | B | B | B | ? |
| 146 | Record media paths in incident | Source present | B | B | B | B | ? |
| 147 | List missing media in manifest | Source present | ? | ? | ? | ? | ? |
| 148 | Allow independent external file rehashing | Source present | ? | ? | ? | ? | ? |
| 149 | Retain media provenance metadata | Source present | ? | ? | ? | ? | ? |
| 150 | No cryptographic signature certificate (not implemented) | Not implemented | ? | ? | ? | ? | ? |
| 151 | No trusted time-stamp authority (not implemented) | Not implemented | ? | ? | ? | ? | ? |
| 152 | No external chain-of-custody attestation (not implemented) | Not implemented | ? | ? | ? | ? | ? |

**152 individual items in Part 1.** [Part 2](FEATURE-MATRIX-2.md) continues with exports, sharing, controls, diagnostics, monetization, privacy and release compliance.

**Interpretation:** Competitor-marked **B** refers to broad marketing categories only. No competitor's code was inspected; a question mark is not a negative result. [Methodology](METHODOLOGY.md).