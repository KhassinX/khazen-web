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
updated: 2026-06-09
---

# Privacy Policy — Khazen

**Effective date**: 2026-06-09
**App**: Khazen ([App Store](https://apps.apple.com/app/khazen/id6761610239))
**Data controller**: KHASSINX LLC, a Florida limited liability company (United States)
**Contact**: legal@khassinx.com

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

To show your transactions, Khazen connects to your financial institutions through **Plaid Inc.** ("Plaid"), a regulated financial-data network used widely by U.S. banks and fintech apps. When you link an account:

- You enter your bank credentials **directly into Plaid's secure interface**. **Khazen never sees or stores your bank login.** Plaid authenticates with your bank using your bank's standards (OAuth where your bank supports it).
- Plaid returns the account and transaction data you choose to share, on a **read-only** basis. The access tokens that let Khazen refresh your data are encrypted in transit and at rest, and we revoke them when you disconnect a bank or delete your account.
- **Khazen is not a bank, money transmitter, broker, lender, or financial institution.** It does not hold or move your money. It reads the information you choose to connect and helps you organize it — that is all.

We act as a **passthrough**. Your bank data flows from your bank, through Plaid, to our backend, then to your device. Our backend does not enrich your data with third-party datasets, does not build an advertising profile, and does not share your data with anyone.

Plaid is an independent service; its handling of your information is governed by the **[Plaid End User Privacy Policy](https://plaid.com/legal/#end-user-privacy-policy)**, which you also accept within Plaid's connection flow. Khazen's use of the Plaid name is solely to identify Plaid as the service that powers bank connections, and does not imply any partnership, sponsorship, or endorsement by Plaid Inc.

## Where your data lives

| What | Where |
|---|---|
| Transactions, accounts, budgets, goals, recurring detection | Local SwiftData store on your device + **your personal iCloud** (encrypted, your Apple ID) |
| Bank-connection tokens (Plaid access tokens) | Encrypted at rest in our backend + on-device Keychain |
| Subscription entitlement | Verified locally via Apple StoreKit 2 + server cross-check |
| Push device tokens | Backend table indexed by your opaque Apple ID identifier |
| App preferences (categories, currency, theme) | Local + iCloud Key-Value Store |

iCloud sync uses **your** Apple ID. We never see, access, or have any way to retrieve the iCloud-synced data. Apple encrypts it in transit and at rest. If you delete the app and remove the iCloud data, that copy is gone. The only thing we keep on our own servers is the bank-connection token needed to refresh your transactions — scoped to that purpose, and we revoke it when you disconnect the bank or delete your account.

## Service providers

We don't sell or share your personal information. To run Khazen we rely on a few service providers that process data only on our behalf, only for the purposes below, and under contract to protect it:

- **Bank connectivity — Plaid Inc.** connects your financial accounts on a read-only basis (see [Bank account connections](#bank-account-connections) above).
- **Payments — Apple Inc.** processes all purchases and subscriptions through the App Store; we never receive your card details.
- **Cloud infrastructure providers (United States)** host our backend and store the connection tokens needed to refresh your data. Your data is stored and processed in the United States.
- **Content-delivery, DNS and security providers** serve our website and protect it from abuse; in routing and securing traffic, limited technical connection data (such as IP address) may be processed transiently on globally distributed edge infrastructure.

These providers may use your information only to provide services to us, and may not sell or share it.

## Data retention

We keep your data only as long as it serves the purpose you gave it for:

- **Bank-connection tokens** — until you disconnect the bank or delete your account.
- **Push notification token** — while you have notifications turned on.
- **Subscription status** — while your account exists.
- **Email you send us** — only as long as needed to handle your message.
- **Your transactions, balances, budgets and goals** — these live on your device and in your own iCloud, never on our servers.

When you delete your account, we remove your records and close the bank connections you linked.

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

**If your subscription lapses:** your bank connections pause rather than disconnect, so that if you resubscribe soon, your accounts reconnect at no extra cost. If you don't, the connections are closed automatically. You can disconnect manually at any time.

## Notifications and email

- **Push notifications**: opt-in. If you allow them, your device receives an Apple Push Notification token that we store keyed to your opaque Apple ID identifier. Notifications are scoped strictly to what you enable in-app (budget warnings, low balance alerts, etc.). We do not send marketing pushes.
- **Email**: if you write to us at any `@khassinx.com` address, we receive your message and reply address through our email provider. We retain that correspondence to handle the conversation and any follow-up. We do not add you to any mailing list. Khazen has no mailing list.

## Children's privacy

Khazen is intended for users **13 and older** (App Store rating accordingly). We do not knowingly collect data from children under 13. If you believe a child under 13 has used Khazen, contact us at legal@khassinx.com and we will remove all associated data promptly.

## Your rights

You have the right to:

- **Access** your data — visible in the app at all times.
- **Delete** your account — one tap from in-app Settings → Account → Delete account. This removes your records from our backend and closes the bank connections you linked. iCloud-synced data is removed from your iCloud when you delete the app and clear its data from your Apple ID.
- **Disconnect** individual bank connections at any time without deleting your account.
- **Object** to any data processing — write to legal@khassinx.com.
- **Portability** — your data is yours; to request a copy, email [`legal@khassinx.com`](mailto:legal@khassinx.com).

**California residents:** we **do not sell or share** your personal information (as those terms are defined under the CCPA/CPRA), and have not in the past 12 months. To exercise California privacy rights, email [`legal@khassinx.com`](mailto:legal@khassinx.com).

For the full set of region-specific rights — the EU/EEA (GDPR), the UK, Spain (LOPDGDD), California (CCPA/CPRA), other US states, and the rest of the world — and how they apply, see KhassinX's [Privacy Rights](https://khassinx.com/legal/your-rights/). To exercise any of them for Khazen, use the in-app controls above or email [`legal@khassinx.com`](mailto:legal@khassinx.com).

## Apple App Privacy Nutrition Labels

In the App Store listing, Khazen declares the data categories it actually touches — currently Financial Info, Identifiers (User ID), Email Address, Name, Device ID, Purchase History, and the notes you add to transactions (Other User Content) — each linked to you and used only for app functionality, never for tracking or advertising. All other categories are Not Collected.

The authoritative list is the one declared in the App Store listing and the app's `PrivacyInfo.xcprivacy` manifest; this policy defers to them, and they are verified against the actual code (no analytics SDKs, no third-party trackers, no advertising frameworks).

## Security

- All data in transit uses **TLS 1.2+**.
- Bank access tokens are encrypted at rest in our backend.
- Backend access is scoped to the minimum permissions required, and sensitive endpoints are protected by Apple App Attest device attestation together with Sign in with Apple — requests that aren't from the genuine Khazen app are rejected.
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

- Notify the relevant authorities within the timeframe required by applicable law, where such notification is required.
- Notify affected users **without undue delay** through an in-app alert at next launch and, where we have an email on file, via email.
- Publish a public post-mortem on this site at `/security/incidents/` once mitigation is complete.

We have not experienced a breach to date. This commitment establishes the process if one occurs.

## Jurisdiction

This policy is governed by the laws of the **State of Florida, United States** — the jurisdiction in which KHASSINX LLC is formed. Disputes are resolved under those laws.

## Trademarks

Apple, the Apple logo, iPhone, iPad, Apple Watch, Mac, and StoreKit are trademarks of Apple Inc., registered in the U.S. and other countries and regions. App Store and iCloud are service marks of Apple Inc. Apple Intelligence is a trademark of Apple Inc. Use of the "Sign in with Apple" name is subject to Apple's guidelines. Plaid is a trademark of Plaid Inc. All other trademarks are the property of their respective owners. Khazen is a product of KHASSINX LLC and is not affiliated with, endorsed by, or sponsored by these companies beyond the services described in this policy.

## Contact

If you have any privacy concerns or questions:

- **Email**: legal@khassinx.com
- **Mail**: Available on written request via email

We aim to respond within seven business days.

---

*Last updated: 2026-06-09 · Version 1.1*
