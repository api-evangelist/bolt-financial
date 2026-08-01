---
name: bolt-financial-charge-and-settle
description: Take a Bolt cart from order token through authorization, capture, refund and void, handling fraud-review states and Bolt's idempotency contract correctly.
api: openapi/bolt-financial-bolt-api-openapi.yml
operations:
  - createOrderToken
  - authorizeTransaction
  - captureTransaction
  - refundTransaction
  - voidTransaction
  - reviewTransaction
  - getTransactionDetails
generated: '2026-07-31'
method: generated
source: openapi/bolt-financial-bolt-api-openapi.yml + conventions/bolt-financial-conventions.yml
---

# Charge and settle a Bolt transaction

Bolt's own `bolt-api-verify` skill applies here first: confirm every path, method and required
field against `https://assets.boltapp.com/external-api-references/bolt.yml` before calling.
If the spec does not define a field, mark it BLOCKED — do not guess.

## Setup

- Base URL: `https://api-sandbox.boltapp.com` in development, `https://api.boltapp.com` in
  production. Keys and transactions never cross environments.
- Every request carries `X-Api-Key`, a fresh `X-Nonce` (unique 12–16 digit value, UUID is
  fine) and `Content-Type: application/json`.
- Every `POST` and `PATCH` carries an `Idempotency-Key` (UUID, ≤255 chars). Keys live 24
  hours and only match on an identical URL, method, body and key headers.

## Steps

1. **Mint an order token.** `createOrderToken` (`POST /v1/merchant/orders`) turns the
   merchant cart into a Bolt order token. This is the handoff point between the merchant's
   cart of record and Bolt.
2. **Authorize.** `authorizeTransaction` (`POST /v1/merchant/transactions/authorize`).
   The response — and the webhook that follows — puts the transaction in one of five
   states: `pending` (in fraud review), `failed_payment`, `payment` (auto-capture, done),
   `auth` (manual capture, ready), `rejected_irreversible` or `rejected_reversible`.
   Do not treat a 2xx as "paid": read the status.
3. **Capture** when using manual capture. `captureTransaction`
   (`POST /v1/merchant/transactions/capture`). Emits a `capture` webhook, status
   `Completed`.
4. **Appeal a reversible rejection** if the merchant wants it. `reviewTransaction`
   (`POST /v1/merchant/transactions/review`). Only `rejected_reversible` is appealable;
   `rejected_irreversible` is final.
5. **Refund** with `refundTransaction` (`POST /v1/merchant/transactions/credit`) — emits a
   `credit` webhook, status `Refunded`. **Void** an uncaptured authorization with
   `voidTransaction` (`POST /v1/merchant/transactions/void`) — emits a `void` webhook,
   status `Cancelled`.
6. **Read state** at any point with `getTransactionDetails`
   (`GET /v1/merchant/transactions/{REFERENCE}`), and attach merchant metadata with
   `updateTransaction` (`PATCH /v1/merchant/transactions/{REFERENCE}`).

## Retry rules

Bolt's idempotency middleware covers 4xx and 5xx responses, so a retry with the same key and
body returns the same status.

| Situation | Action |
|---|---|
| `Idempotent-Retriable: true` | Back off, retry with the **same** key |
| Rate limited (`429`, code `35` / `41`) | Back off, retry with the **same** key |
| Network error / no response | Retry with the **same** key |
| Content error (`400`) | Fix the request, retry with a **new** key |
| `409` concurrent identical key | Wait for the original to terminate, then use its cached response |
| `500` | Check https://status.bolt.com, contact Bolt Support |

`Idempotent-Replayed: true` on a response means you are reading a cached result, not a new
side effect. Errors are numeric Bolt codes with a code name and a shopper-facing prompt —
see `errors/bolt-financial-error-codes.yml`.

## Sandbox

Drive outcomes deterministically with the published values in
`sandbox/bolt-financial-sandbox.yml`: card `4111 1111 1111 1111` approves,
`4111 1111 1111 1012` declines, anything ending `0001` is rejected in pre-authorization, and
order totals `$8,017.01`–`$8,017.05` select review/approve/reject/decline outcomes.

## Set `skip_hook_notification`

Transaction endpoints accept `skip_hook_notification: true` to suppress the resulting
webhook. Only set it when the caller is deliberately reconciling by polling instead.
