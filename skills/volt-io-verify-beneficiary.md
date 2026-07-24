---
name: Verify a beneficiary account before payout
description: Retrieve an account holder verification (VoP/CoP) result and approve or reject it as a gate before releasing a payout.
api: openapi/volt-io-accounts-openapi-original.yaml
operations: [get-account-holder-verification-details, approve-account-holder-verification, reject-account-holder-verification]
---

# Verify a beneficiary account before payout

Volt Accounts supports account holder verification (Verification of Payee /
Confirmation of Payee) to confirm beneficiary ownership and reduce misdirected
payments before funds are released.

## Prerequisites
- OAuth2 Bearer JWT (see `conventions/volt-io-conventions.yml`).

## Steps
1. **Read the verification result.** Call `get-account-holder-verification-details`
   to retrieve the `VerificationResult` (name-match outcome) for the beneficiary.
2. **Decide.** Based on the match outcome:
   - Call `approve-account-holder-verification` to accept the beneficiary and let
     the payment proceed, or
   - Call `reject-account-holder-verification` to block it.
3. **Proceed to payout** only after an approval — see
   `skills/volt-io-create-payout.md`.

## Rules
- Treat a partial/no match as high-risk; require explicit human approval before
  approving (this is a funds-movement gate).
- Errors follow `errors/volt-io-problem-types.yml`.
