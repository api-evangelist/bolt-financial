---
name: bolt-gaming-docs
description: Integrate Bolt Gaming checkout links, Unity and JavaScript SDKs, webhooks, and interactive ads. Use when building in-game payments or gaming storefronts.
---

# Bolt gaming integration

## Start here

| Topic | Doc |
|-------|-----|
| Quickstart | https://help.boltapp.com/gaming/guide/quickstart.md |
| Payment links API | https://help.boltapp.com/gaming/guide/payment-links-api.md |
| Webhook validation | https://help.boltapp.com/gaming/guide/bolt-webhooks/validate-authenticity.md |
| Unity SDK | https://help.boltapp.com/gaming/platforms/unity/overview.md |
| JavaScript SDK | https://help.boltapp.com/gaming/platforms/javascript/overview.md |

Full gaming index: https://help.boltapp.com/documentation/browse#gaming

## Conventions

- Create payment links server-side with `POST /v1/gaming/payment_links`; verify the body in `https://assets.boltapp.com/external-api-references/bolt.yml`
- Use sandbox merchant account at merchant-sandbox.boltapp.com for development
- Unity and JavaScript SDKs have separate quickstarts: do not mix platform steps
- CodeGroup labels must match exactly: `Unity C#`, `JavaScript`, `Node.js`, `cURL`

## Auth

- Server requests: `X-Api-Key` and publishable key per gaming API docs
- Webhooks: verify HMAC with signing secret from Merchant Dashboard → Administration → API

## Do not

- Mix gaming payment-link flows with standard eCommerce Checkout plugin docs
- Invent request fields not present in the OpenAPI spec
- Use production keys in sandbox or vice versa
