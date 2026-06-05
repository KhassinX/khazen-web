---
layout: prose
title: Privacy Policy
permalink: /legal/privacy/
lang: en
canonical_en: /legal/privacy/
canonical_es: /es/legal/privacy/
redirect_from:
  - /PRIVACY_POLICY
  - /PRIVACY_POLICY/
  - /privacy
  - /privacy/
updated: 2026-05-26
---

# Privacy Policy — Khazen

**Effective date**: 2026-05-26
**App**: Khazen ([App Store](https://apps.apple.com/app/khazen/id6761610239))
**Developer**: KHASSINX LLC
**Contact**: hello@khassinx.com

---

## TL;DR

Khazen is a personal finance app. To work, it connects to your bank accounts and stores transactions on your devices and in your personal iCloud. We do not sell, share, or monetize your financial data. We do not run advertising, analytics, or tracking. Our backend exists only to relay bank connections — it never powers an advertising profile of you.

You can disconnect any bank at any time. You can delete your account in one tap, which removes everything we hold about you.

---

## Quick map of what is collected

| Category | Collected? | Purpose |
|---|---|---|
| Bank account data (balances, transactions, account names) | ✅ Yes | App functionality — show your money in the app |
| Apple ID identifier | ✅ Yes (opaque, for sync) | iCloud sync across your devices |
| Email address | Only if you contact us | Reply to your message |
| Subscription status | ✅ Yes (via Apple) | Verify entitlement to paid features |
| Device push token | ✅ Yes | Send you only the notifications you opt into |
| Crash logs | ❌ No | We do not collect crash reports |
| Usage analytics | ❌ No | No analytics SDKs of any kind |
| Advertising identifiers (IDFA) | ❌ No | We do not use them |
| Location | ❌ No | We do not request or use location |
| Contacts / Photos / Microphone / Camera | ❌ No | Khazen does not access these |

The app's `PrivacyInfo.xcprivacy` manifest declares the same data categories. Apple verifies this during App Store review.

## Bank account connections

To show your transactions, Khazen connects to your financial institutions through a **regulated financial data network** widely used by U.S. banks and fintech apps. This network:

- Authenticates with **your bank directly** using your bank's standards (OAuth where supported by your bank, otherwise the network's secure flow). Khazen never sees your bank credentials.
- Returns short-lived access tokens that are encrypted in transit and at rest.
- Honors disconnect requests immediately — when you remove a bank in Khazen, the access token is revoked.

We act as a **passthrough**. Your bank data flows from your bank to the network, then to our backend, then to your device. Our backend does not enrich your data with third-party datasets, does not build an advertising profile, does not share your data with anyone.

The network's own privacy practices are governed by their published policies, available to you when you connect each institution.

## Where your data lives

| What | Where |
|---|---|
| Transactions, accounts, budgets, goals, recurring detection | Local SwiftData store on your device + **your personal iCloud** (encrypted, your Apple ID) |
| Cached financial network access tokens | Encrypted at rest in our backend + on-device Keychain |
| Subscription entitlement | Verified locally via Apple StoreKit 2 + server cross-check |
| Push device tokens | Backend table indexed by your opaque Apple ID identifier |
| App preferences (categories, currency, theme) | Local + iCloud Key-Value Store |

iCloud sync uses **your** Apple ID. We never see, access, or have any way to retrieve the iCloud-synced data. Apple encrypts it in transit and at rest. If you delete the app and remove the iCloud data, that copy is gone — and there is no other copy on any server we control besides the bank access tokens (which are scoped only to allow re-fetching new transactions and are revoked the moment you disconnect a bank).

## Apple Intelligence (on-device AI)

When supported by your device, Khazen uses **Apple Intelligence (FoundationModels)** to generate financial insights, categorize transactions, and write summaries.

This model runs **entirely on your device**. Your transactions, balances, and personal context never leave your iPhone, iPad, or Mac for AI inference. We do not send your data to OpenAI, Anthropic, Google, or any third-party AI service. We do not have an AI server of our own either.

Apple Intelligence eligibility requires iOS 26+ and a recent device. On devices without Apple Intelligence, Khazen's AI features are silently hidden, and the rest of the app works normally.

## Subscription and purchases

Subscriptions are processed by **Apple StoreKit 2**. We receive only:

- A boolean: this Apple ID has an active subscription (via `Transaction.currentEntitlements`)
- The current product (monthly or yearly tier)
- Renewal and revocation dates (to honor cancellations and refunds promptly)

We do **not** see your name, payment method, billing address, or any other purchase metadata. Apple handles all of that. Refunds and subscription management go through Apple directly (Settings → Apple ID → Subscriptions).

Free trial: seven days, no auto-charges during the trial period. We send local notifications before the trial ends so there are no surprise renewals.

## Notifications and email

- **Push notifications**: opt-in. If you allow them, your device receives an Apple Push Notification token that we store keyed to your opaque Apple ID identifier. Notifications are scoped strictly to what you enable in-app (budget warnings, low balance alerts, etc.). We do not send marketing pushes.
- **Email**: if you write to us at any `@khassinx.com` address, we receive your message and reply address through our email provider. We retain that correspondence to handle the conversation and any follow-up. We do not add you to any mailing list. Khazen has no mailing list.

## Children's privacy

Khazen is intended for users **13 and older** (App Store rating accordingly). We do not knowingly collect data from children under 13. If you believe a child under 13 has used Khazen, contact us at hello@khassinx.com and we will remove all associated data promptly.

## Your rights

You have the right to:

- **Access** your data — visible in the app at all times. Export available from in-app Settings.
- **Delete** your account — one tap from in-app Settings → Account → Delete account. This removes your data from our backend (bank tokens, push tokens, subscription cross-check) within minutes and is verifiable. iCloud-synced data is removed from your iCloud automatically when you delete the app and clear its data from your Apple ID.
- **Disconnect** individual bank connections at any time without deleting your account.
- **Object** to any data processing — write to hello@khassinx.com.
- **Portability** — export your transactions and accounts from in-app Settings (CSV format).

For users in the **European Union (GDPR)** and **California (CCPA)**: you have the additional rights conferred by those regulations. Write to hello@khassinx.com to exercise them.

## Apple App Privacy Nutrition Labels

In the App Store listing, Khazen declares data categories aligned with this policy:

- **Financial Info**: Collected — Linked to you, Used for app functionality
- **Identifiers (User ID)**: Collected — Linked to you, Used for app functionality
- **Other User Content**: Collected — Linked to you, Used for app functionality (notes you add to transactions)
- All other categories: Not Collected

This is verified against the in-app `PrivacyInfo.xcprivacy` manifest and the actual code (no analytics SDKs, no third-party trackers, no advertising frameworks).

## Security

- All data in transit uses **TLS 1.2+**.
- Bank access tokens are encrypted at rest in our backend.
- Backend access is scoped to the minimum permissions required and protected by Apple App Attest device attestation — requests from outside the genuine Khazen app are rejected.
- iCloud sync uses Apple's end-to-end encryption where you have enabled Advanced Data Protection.

To report a vulnerability, see our [Security & Responsible Disclosure](/security/) policy.

## International transfers

Khazen's backend operates in the United States. If you use Khazen from outside the U.S., your bank access tokens and other backend records may be processed in the United States. We do not transfer your data to any other country for processing.

## Changes to this policy

We may update this policy when:

- Adding new features that materially change data handling
- Reflecting changes in Apple App Store policies
- Correcting legal or factual errors

Material changes will be reflected with a new "Effective date" at the top, and a notice will appear in-app at next launch.

## Breach notification

In the event of a confirmed data breach affecting your personal data, we will:

- Notify the relevant supervisory authority within **72 hours** of confirming the incident, where required by applicable law (including GDPR Art. 33 for EU residents).
- Notify affected users **without undue delay** through an in-app alert at next launch and, where we have an email on file, via email.
- Publish a public post-mortem on this site at `/security/incidents/` once mitigation is complete.

We have not experienced a breach to date. This commitment establishes the process if one occurs.

## Jurisdiction

This policy is governed by the laws of the operator's registered place of business in the United States. Disputes are resolved under those laws.

## Contact

If you have any privacy concerns or questions:

- **Email**: hello@khassinx.com
- **Mail**: Available on written request via email

We aim to respond within seven business days.

---

*Last updated: 2026-05-26 · Version 1.0*
