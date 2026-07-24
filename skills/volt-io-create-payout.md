---
name: Create a payout from a Volt Account
description: Authenticate, resolve the source Volt Account, and create an idempotent payout transaction to a beneficiary, then confirm status.
api: openapi/volt-io-accounts-openapi-original.yaml
operations: [get-accounts, get-account-details, create-transaction, get-transaction-details]
---

# Create a payout from a Volt Account

Use this skill to move funds out of a Volt Account to a beneficiary bank account
(payout / settlement / internal transfer) via the Volt Accounts API.

## Prerequisites
- OAuth2 access token. Obtain it with `POST /oauth` on `gateway.volt.io` using
  your `client_id`, `client_secret`, API `username` and `password` (from Fuzebox).
  Send it as `Authorization: Bearer <JWT>` on every call.
- Base host: `https://accounts.sandbox.volt.io` (test) or `https://accounts.volt.io` (live).

## Steps
1. **Find the source account.** Call `get-accounts` to list Volt Accounts, or
   `get-account-details` with a known `accountId` to confirm status and balance.
2. **Create the payout.** Call `create-transaction` with a `PayoutTransactionRequest`
   (or `SettlementTransactionRequest` / `InternalTransactionRequest` as appropriate):
   set the source `accountId`, the beneficiary `AccountIdentifier`
   (IBAN+BIC or accountNumber+sortCode), and `amount` in **minor units** (integer).
   - **Always send an `Idempotency-Key` header** (a UUID). Retrying with the same
     key returns `409 Conflict` instead of creating a duplicate payout.
3. **Confirm.** Poll `get-transaction-details` with the returned `transactionId`,
   or subscribe to account payment webhooks, until the transaction reaches a
   terminal `TransactionStatusEnum` value.

## Rules
- Amounts are integers in minor units (e.g. `100` = 1.00 EUR).
- Payload keys are case-sensitive; HTTP header names are case-insensitive.
- Outgoing payments may require JWS request signing — see
  `conventions/volt-io-conventions.yml`.
- Handle errors per `errors/volt-io-problem-types.yml` (422 carries typed field
  validation constraints; 409 signals a state conflict or replayed idempotency key).
