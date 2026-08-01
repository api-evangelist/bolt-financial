---
name: bolt-financial-webhooks-and-tokenizer
description: Register and verify Bolt webhooks, react to the transaction event set, and tokenize a card client-side against the Bolt Tokenizer so raw PAN data never reaches the merchant server.
api: openapi/bolt-financial-bolt-api-openapi.yml
operations:
  - createWebhook
  - queryWebhooks
  - getWebhook
  - deleteWebhook
  - tokenizerPublicKey
  - tokenizerToken
  - getTransactionDetails
generated: '2026-07-31'
method: generated
source: openapi/bolt-financial-bolt-api-openapi.yml + openapi/bolt-financial-tokenizer-openapi.yml + asyncapi/bolt-financial-webhooks.yml
---

# Bolt webhooks and card tokenization

Two surfaces that sit either side of the transaction: how money data gets in safely, and how
state changes get back out.

## Tokenize a card

The Tokenizer lives on a **different host** (`bolttk.com`), deliberately, so card data never
touches the merchant backend.

1. `tokenizerPublicKey` (`GET /public_key`) — fetch the RSA public key.
2. Encrypt the card payload client-side with that key.
3. `tokenizerToken` (`POST /token`) — exchange the encrypted payload for a Bolt payment
   token.
4. Use that token with `authorizeTransaction` on the Bolt API host.

Hosts: `https://sandbox.bolttk.com` (sandbox), `https://production.bolttk.com` (production).
Never send raw PAN data to `api.boltapp.com`.

## Register webhooks

- `createWebhook` (`POST /v1/webhooks`) — register an endpoint.
- `queryWebhooks` (`GET /v1/webhooks`) — list what is registered.
- `getWebhook` (`GET /v1/webhooks/{webhook_id}`) — read one.
- `deleteWebhook` (`DELETE /v1/webhooks/{webhook_id}`) — remove one.

Registration is also available from the Merchant Dashboard under Administration → API.

## Verify every delivery before acting on it

Bolt signs each webhook HMAC-SHA256 with the merchant **Signing Secret** and puts the
signature in `X-Bolt-Hmac-Sha256`. During a secret rotation Bolt also sends
`X-Bolt-Hmac-Sha256-Pending` signed with the incoming key — accept either while the pair is
active. Reverting to the previous secret is possible for up to 48 hours.

Reject any payload whose signature does not verify. Do not trust the body's contents to
identify the transaction; re-read it with `getTransactionDetails`.

## The event set

| Event | Group | Transaction status |
|---|---|---|
| `pending` | authorization | Pending (in fraud review) |
| `failed_payment` | authorization | Failed |
| `payment` | authorization | Completed (auto-capture) |
| `auth` | authorization | Authorized (manual capture) |
| `rejected_irreversible` | authorization | Permanently Rejected |
| `rejected_reversible` | authorization | Recently Rejected (appealable) |
| `capture` | merchant-initiated | Completed |
| `credit` | merchant-initiated | Refunded |
| `void` | merchant-initiated | Cancelled |
| `newsletter_subscription` | other | — |
| `risk_insights` | other | — |
| `credit_card_deleted` | beta | — |

`authorizeTransaction`, `captureTransaction`, `refundTransaction` and `voidTransaction` all
trigger webhooks by default; pass `skip_hook_notification: true` to suppress.

## Rules

- Handlers must be idempotent on their own side: Bolt may redeliver, and the transaction
  reference is the natural dedupe key.
- Bolt publishes no AsyncAPI document — the catalog above is transcribed from
  `https://help.boltapp.com/developers/webhooks/webhooks/` into
  `asyncapi/bolt-financial-webhooks.yml`.
- Virtual Terminal transactions do **not** emit webhooks; use SMS or email notifications for
  those.
- Review failed deliveries at
  `https://help.boltapp.com/developers/webhooks/webhook-failure-notifications/`.
