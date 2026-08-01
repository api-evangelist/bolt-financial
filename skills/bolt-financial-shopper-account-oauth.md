---
name: bolt-financial-shopper-account-oauth
description: Authorize a Bolt shopper account with OAuth 2.0 / OIDC and read or modify the shopper's profile, addresses and stored payment methods.
api: openapi/bolt-financial-bolt-api-openapi.yml
operations:
  - OAuthToken
  - getAccount
  - createAccount
  - detectAccount
  - updateAccountProfile
  - addAddress
  - editAddress
  - replaceAddress
  - deleteAddress
  - addPaymentMethod
  - deletePaymentMethod
generated: '2026-07-31'
method: generated
source: openapi/bolt-financial-bolt-api-openapi.yml + scopes/bolt-financial-scopes.yml
---

# Authorize a Bolt shopper and manage their account

Bolt's shopper account network is the identity layer behind one-click checkout. Reaching a
shopper's data requires the shopper's own OAuth consent, not just the merchant API key.

## Never call /authorize yourself

The store opens the **Bolt Login client**; the shopper authenticates and consents inside it;
the client returns an authorization code to the store front end. Your code starts at the
token exchange.

## Steps

1. **Check whether the shopper already has a Bolt account.** `detectAccount`
   (`GET /v1/account/exists`). Use this before offering account creation.
2. **Create one if not.** `createAccount` (`POST /v1/account`).
3. **Exchange the authorization code.** `OAuthToken` (`POST /v1/oauth/token`).
   - `client_id` is the merchant **publishable key**; `client_secret` is the merchant
     **API key**.
   - The authorization code is single-use and valid for **5 minutes**.
   - You receive an access token (**1 hour**), a single-use refresh token (**1 year**), and
     an ID token when `openid` was requested.
4. **Call account APIs with the shopper token.** Present it as
   `Authorization: Bearer ${TOKEN}`.
   - `getAccount` (`GET /v1/account`) — profile, addresses, payment methods.
   - `updateAccountProfile` (`PATCH /v1/account/profile`).
   - `addAddress` (`POST /v1/account/addresses`), `editAddress`
     (`PUT /v1/account/addresses/{id}`), `replaceAddress`
     (`POST /v1/account/addresses/{id}`), `deleteAddress`
     (`DELETE /v1/account/addresses/{id}`).
   - `addPaymentMethod` (`POST /v1/account/payment_methods`), `deletePaymentMethod`
     (`DELETE /v1/account/payment_methods/{payment_method_id}`).

## Scopes

| Scope | Grants |
|---|---|
| `bolt.account.view` | Read-only actions on Bolt Account data |
| `bolt.account.manage` | Read / edit / delete actions on Bolt Account data |
| `openid` | An ID token JWT for Bolt SSO |
| `email` | Advertised by the OIDC discovery document (not declared in the OpenAPI) |

Request `bolt.account.view` when you only read. Discovery lives at
`https://api.boltapp.com/.well-known/openid-configuration`; ID tokens are RS256 and the JWKS
is at `https://api.boltapp.com/v1/oauth/jwks.json`.

## Rules

- Idempotency applies: `addAddress`, `addPaymentMethod`, `createAccount`,
  `updateAccountProfile` and `replaceAddress` are POST/PATCH, so send an
  `Idempotency-Key`. Bolt's own documentation uses `POST /v1/account/addresses` as the
  worked example.
- Refresh tokens are **single use** — persist the new one every exchange or the shopper has
  to re-consent.
- Never store the merchant API key client-side; it doubles as the OAuth client secret.
- Auth failures come back as Bolt codes `1001`–`1015` (see
  `errors/bolt-financial-error-codes.yml`), not as an OAuth error envelope.
