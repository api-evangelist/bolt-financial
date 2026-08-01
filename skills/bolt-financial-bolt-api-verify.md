---
name: bolt-api-verify
description: Verify API examples, env vars, and endpoint paths against OpenAPI specs before implementing Bolt integrations. Use when writing checkout, webhook, or gaming API code.
---

# Bolt API verify

## Spec locations

| API | Spec |
|-----|------|
| Bolt (outbound) | `https://assets.boltapp.com/external-api-references/bolt.yml` |
| Embeddable v1 | `https://assets.boltapp.com/external-api-references/embedded.yml` |
| Tokenizer | `https://assets.boltapp.com/external-api-references/tokenizer.yml` |

For inbound callbacks (cart, shipping, tax), see [Merchant Callback](https://help.boltapp.com/api-reference/merchant-callback/overview).

## Before calling an endpoint

1. Confirm path, method, and required fields in the OpenAPI spec
2. Include `X-Api-Key` and `X-Nonce` on every outbound request unless the spec says otherwise
3. Use sandbox URLs (`api-sandbox.boltapp.com`, `connect-sandbox.boltapp.com`) for development
4. If the spec does not define a field or behavior, mark **BLOCKED**: do not guess

## Version policy

- Default to **Embeddable API v1** (`embedded.yml`) for custom checkout UI
- Do not use v3 unless your Bolt contact explicitly enables it

## Environments

| | Sandbox | Production |
|--|---------|------------|
| API | api-sandbox.boltapp.com | api.boltapp.com |
| CDN | connect-sandbox.boltapp.com | connect.boltapp.com |
| Dashboard | merchant-sandbox.boltapp.com | merchant.boltapp.com |

Keys and transactions do not cross environments.
