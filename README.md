# Volt (volt-io)

Volt is a London-headquartered real-time payments company that operates a global account-to-account (A2A) "pay by bank" network built on open banking rails. Founded in 2019 and FCA-authorised in its home market of the United Kingdom, Volt connects merchants and PSPs to bank-initiated payments across the UK (Faster Payments / Open Banking under PSD2), Europe (SEPA), Brazil (Pix), Australia (PayTo), and other real-time schemes through a single API — so shoppers pay directly from their bank account without cards.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/volt-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/volt-io/refs/heads/main/apis.yml)

## Tags

- Payments
- United Kingdom
- Open Banking
- Account-to-Account
- Real-Time Payments
- Payment Initiation
- Payouts
- Recurring Payments
- Cross-Border
- Pay by Bank

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

Volt exposes an API-native developer surface at [docs.volt.io](https://docs.volt.io/), with a single production gateway host `https://gateway.volt.io` (sandbox `https://gateway.sandbox.volt.io`) and OAuth2 authentication. The documented product API family:

### Volt Payments API

Global Payments API that initiates account-to-account (pay by bank) payments across open-banking and real-time schemes (UK Faster Payments, SEPA, Pix, PayTo and more), creating payments, retrieving status, and handling refunds.

- **Human URL:** [https://docs.volt.io/api-reference/payments](https://docs.volt.io/api-reference/payments)
- **Base URL:** `https://gateway.volt.io`

### Volt Mandates API

Manages recurring account-to-account payments including variable recurring payments (VRP) and mandate lifecycle.

- **Human URL:** [https://docs.volt.io/api-reference/mandates](https://docs.volt.io/api-reference/mandates)
- **Base URL:** `https://gateway.volt.io`

### Volt Accounts API

Powers Volt Accounts and virtual IBANs for settlement, collections, payouts and refunds — programmatic named accounts for receiving and disbursing funds.

- **Human URL:** [https://docs.volt.io/api-reference/accounts](https://docs.volt.io/api-reference/accounts)
- **Base URL:** `https://gateway.volt.io`

### Volt Verify API

Account Identification API that confirms bank account ownership/details before payment (confirmation-of-payee style checks).

- **Human URL:** [https://docs.volt.io/api-reference/verify](https://docs.volt.io/api-reference/verify)
- **Base URL:** `https://gateway.volt.io`

### Volt Reporting API

The Reporter API exposes transaction, settlement and reconciliation data across the Volt platform.

- **Human URL:** [https://docs.volt.io/api-reference/reporter](https://docs.volt.io/api-reference/reporter)
- **Base URL:** `https://gateway.volt.io`

### Volt Authentication API

Issues OAuth2 access tokens for the gateway. A POST to `/oauth` exchanges `client_id`, `client_secret` and `username`/`password` (resource-owner password grant) for a Bearer `access_token`.

- **Human URL:** [https://docs.volt.io/api-reference/authentication/post-oauth](https://docs.volt.io/api-reference/authentication/post-oauth)
- **Base URL:** `https://gateway.volt.io`

## API Posture

- **Developer portal:** confirmed live — [volt.io/developers](https://volt.io/developers/) and [docs.volt.io](https://docs.volt.io/) (both HTTP 200).
- **OpenAPI:** the API reference is OpenAPI-backed (custom Next.js, rendered server-side) but no downloadable OpenAPI/Swagger document is served at a fetchable URL — 0 specs harvested.
- **Auth:** OAuth2 resource-owner password grant → Bearer tokens.
- **Webhooks:** documented for asynchronous payment/account events.
- **Home market:** United Kingdom (FCA-authorised).

## Common Properties

- [Website](https://volt.io/)
- [Developer Portal](https://volt.io/developers/)
- [Documentation](https://docs.volt.io/)
- [API Reference](https://docs.volt.io/api-reference)
- [Getting Started](https://docs.volt.io/get-started)
- [Status Page](https://status.volt.io/)
- [Blog / Content Hub](https://volt.io/content-hub/)
- [Newsroom](https://volt.io/newsroom/)
- [Login (Fuzebox)](https://fuzebox.volt.io/)
- [Support](https://volt.io/contact/)
- [Terms of Service](https://volt.io/legal/terms/)
- [Privacy Policy](https://volt.io/legal/privacy/)
- [LinkedIn](https://www.linkedin.com/company/voltio)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
