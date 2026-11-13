# Lock Witness — Published Pricing, Trial Logic and Entitlement Audit

**Reviewed:** November 13, 2026. **Published source:** [Google Play — Lock Witness](https://play.google.com/store/apps/details?id=com.lockwitness.app). **Inspected private code:** main commit `8ca488aa8b1bdc53b7d2992ca91a436478fe227e`.

## Price numbers verified in the live store listing

| Product | Published Google Play description | Actual purchase independently verified? |
|---|---:|---|
| Pro Monthly | **$2.99 per month**, auto-renewing | **No** |
| Pro Annual | **$19.99 per year**, auto-renewing | **No** |
| Pro Lifetime | **$39.99 one-time** | **No** |
| Trial | **7 days** | Timer implemented; live account/trial eligibility not independently tested |

These are current **advertised** amounts from the product listing, not a verified on-device checkout quote, payment receipt or account entitlement.

## What the current Kotlin actually enforces

1. `MonetizationRepository.kt` persists the first trial-start timestamp in local DataStore, computes remaining days and reports `isInTrial` and `trialExpired`.
2. `ProFeatureGate.kt` permits **unlimited incident history, video, location and export** when either `state.isPro` **or `state.isInTrial`** is true.
3. `FailedUnlockIncidentCreator.kt` uses this gate for video and location at incident creation; `HistoryScreen.kt` limits visible free history to ten items.
4. `PlayBillingService.kt` queries monthly/annual subscriptions and lifetime in-app purchases, acknowledges paid purchases and exposes a product purchase flow.
5. When billing is unavailable, the state can fall back to non-Pro; the local trial can still be active.
6. The local `LocalIncidentExporter.kt` itself has **no Pro entitlement check**, and the inspected Export screen does not show a definitive entitlement guard before the export method. Thus **end-to-end ZIP export paywall enforcement is not verified from these paths**.

## Conflicting product documentation

The private README says a **seven-day trial unlocks all Pro functions and base monitoring/photo remain free afterwards**, whereas some dated monetization checklist and store-listing draft copy describes a **base-level trial with Pro locked during those seven days** and no ongoing free tier. The **current Kotlin gate** supports *Pro-enabled during an active trial*, and its monitor/photo workflow continues without a Pro check; these cannot simultaneously be described as a strictly base-only trial.

The live Google Play description says **“Try free for 7 days. Then go Pro.”** without establishing the exact free-after-expiry entitlement in a live account. It is an unresolved marketing/implementation consistency issue, **not** a verified store-system fault.

## Additional items requiring product testing

- Whether every published subscription and one-time SKU is active in Play Console.
- Real-user purchase, cancellation, restore and acknowledgement across devices.
- Whether reinstalling the app can restart local-trial eligibility (DataStore is local, not account/server anchored).
- Whether the Export UI can reach an ungated local-export path in every free/trial state.
- Whether the `autoDeleteDays` setting triggers an actual automated purge; current source demonstrates preference persistence, not a verified scheduled deletion worker.
- Whether the hashing toggle changes capture behavior; source hashing exists, but disable-path behavior is not established.
- Whether ad-free is meaningful: source contains an ad placeholder, and no complete production ad implementation was established from inspected code.

**Marketing position until reconciled:** “Seven-day trial, with Pro plans advertised at $2.99/month, $19.99/year and $39.99 lifetime; exact included features and purchases follow the current Google Play interface.” Avoid unconditional claims of either a permanent-free tier or a base-only trial.

[Current Google Play listing](https://play.google.com/store/apps/details?id=com.lockwitness.app) · [Verification report](VERIFICATION-AND-STATUS.md) · [Portfolio brochure](BROCHURE.md)
