# Volt (volt-io)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
