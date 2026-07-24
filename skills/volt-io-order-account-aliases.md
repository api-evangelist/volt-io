---
name: Order and activate Volt Account aliases
description: Order additional account identifiers (aliases) under a Volt Account, track the order to completion, then activate an alias for reconciliation.
api: openapi/volt-io-accounts-openapi-original.yaml
operations: [order-aliases, get-alias-order-status, get-aliases, get-alias-details, change-alias-state]
---

# Order and activate Volt Account aliases

Aliases are extra account identifiers issued under a Volt Account so incoming
payments can be automatically reconciled to a customer or ledger.

## Prerequisites
- OAuth2 Bearer JWT (see `conventions/volt-io-conventions.yml`).
- A provisioned Volt Account `accountId`.

## Steps
1. **Order aliases.** Call `order-aliases` with an `AliasesOrderRequest` for the
   target `accountId`. **Send an `Idempotency-Key` header** (UUID) to make the
   order safe to retry.
2. **Track the order.** Poll `get-alias-order-status` with the returned `orderId`
   until it reaches a terminal `AliasOrderStatusEnum` value.
3. **Fetch the resulting aliases.** Call `get-aliases` for the account, or
   `get-alias-details` for a specific `aliasId`, to read the issued identifiers.
4. **Activate / manage.** Call `change-alias-state` to activate or deactivate an
   alias, and `close-alias` when it is no longer needed.

## Rules
- Alias lifecycle transitions are validated server-side; an invalid transition
  returns `409 Conflict` (see `errors/volt-io-problem-types.yml`).
- Subscribe to account-and-alias ordering + lifecycle webhooks
  (`asyncapi/volt-io-webhooks.yml`) instead of tight polling where possible.
