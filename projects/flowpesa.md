# FlowPesa: a wallet for Uganda

Uganda-first digital wallet and community-finance product. This is my company's product, so the source code stays
private. This page describes it; screenshots and a walkthrough are available on request.

**Stack:** Laravel 12 REST API (Sanctum tokens, MySQL) · React Native / Expo mobile app · Africa's Talking SMS

## What works today
- Sign-up with phone, name and PIN; SMS one-time codes with expiry and single use.
- Wallet balance, internal transfers by @username, transaction history with sender, receiver and channel.
- Deposit flow (mobile money and bank transfer reference), shareable receipts, dark and light mode.
- Tested on real Android and iOS devices.

## What is not done yet (said plainly)
- Live MTN and Airtel Money collection and payout is designed but waiting on business registration.
- Automated test coverage is still thin; hardening (rate limiting, callback verification, audit trail) is planned.

## What I learned
Building a wallet means designing for failure first: idempotent callbacks, PINs hashed rather than stored, tokens
kept in secure storage on the phone, and an honest ledger. The roadmap moves toward a double-entry ledger.

<!-- TODO before publishing: 3-4 screenshots (onboarding, dashboard, send, receipt). Do NOT link the repo. -->
