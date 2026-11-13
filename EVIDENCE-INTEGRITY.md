# Lock Witness — Evidence Capture and Integrity, Examined Step by Step

**Evidence snapshot:** private `Amishgangsta/LockWitness` main commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`. **Audit date:** November 13, 2026.

## Evidence chain inside the application

1. **Credential event** — Android's Device Admin receiver calls `onPasswordFailed` for supported PIN, pattern and password attempts. Biometric failures are outside the Android callback. An Android policy may require minimum attempted credential length.
2. **Incident shell** — the app checks the master monitoring setting and creates a Room record with attempt count, device/app/Android version, time, module selections and initial states.
3. **Photo** — a nonexported foreground camera service asks Camera2 to use the front camera, creates a JPEG in app-private storage, hashes the file and updates its incident.
4. **Optional video** — when permitted by the plan/trial and setting, Camera2/MediaRecorder creates a **silent** MP4 for an allowed 5/10/15/30-second interval. It is hashed and its status is recorded.
5. **Optional location** — the client checks granted coarse/fine permission, queries the latest cached fix from enabled Android location providers, and records latitude, longitude, provider and accuracy. **This is not a guaranteed fresh location fix taken at the moment of the event.**
6. **Separate statuses** — the incident retains photo, video, location, email and share states, including disabled, unavailable and failed conditions rather than implying that every capture succeeds.
7. **Review and export** — the owner opens the on-device record and chooses to generate a local ZIP or share the resulting package manually.

## The ZIP's actual structure

| ZIP member | Inspected purpose |
|---|---|
| `metadata.json` | Export version, incident counts and field-level incident data |
| `incidents.csv` | Tabular events, module results, media paths, fingerprint fields and metadata |
| `hashes.txt` | Recorded photo/video SHA-256 fingerprints and list of missing media |
| `photos/` | JPEG media found and included at export time |
| `videos/` | MP4 media found and included at export time |

The exporter checks whether referenced media files exist and records omissions; it is not a silent assertion that the archive is complete. Phase 14-F reported a 41-MB device-produced ZIP whose **13 photo fingerprints** were independently rehashed and matched.

## What SHA-256 establishes

If a recipient independently recomputes SHA-256 for a file and obtains the same fingerprint **as a trustworthy previously recorded value**, they have strong evidence that the file bytes are unchanged relative to that value. The manifest and archive are both locally produced, so the hash **does not independently establish capture time, identity of a person, authorization history, device clock integrity, authenticity of the original event or legal admissibility**.

This source includes **no independently trusted time-stamping authority, signed forensic certificate, remote write-once evidence vault, or external chain-of-custody audit**.

## Ownership and sharing

The Android manifest has **no INTERNET or RECORD_AUDIO permission**, disables `allowBackup`, and makes the capture service nonexported. The share UI uses an Android `FileProvider` URI, grants temporary read access and opens the owner-selected standard chooser. No automatic email or cloud evidence transmission is implemented.

**The most defensible claim:** *Locally stored, independently rehashable evidence with explicit file-status and export-completeness records*. The phrase *court-certified forensic evidence* is not supported by this source.

[All individual features](FEATURE-MATRIX.md) · [Comparison](COMPARISON.md) · [Verified runtime](VERIFICATION-AND-STATUS.md)
