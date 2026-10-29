# Bolt Financial

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

Bolt Financial, Inc. is an American commerce technology company that gives retailers a one-click, identity-powered checkout backed by a shopper account network, payments processing, tokenization and fraud protection. Merchants integrate Bolt either through platform plugins (Adobe Commerce/Magento, BigCommerce, Salesforce Commerce Cloud, Shopify, WooCommerce) or directly against a REST API surface that covers shopper accounts, order tokens, transaction authorize/capture/refund/void, subscriptions, product catalog, merchant statements, webhooks and a hosted card tokenizer. Bolt publishes OpenAPI 3.0 definitions for its Bolt API, Embeddable Checkout v1 and v3, and Tokenizer endpoints, ships first-party SDKs for TypeScript, Python, C#, Go, PHP, iOS/Swift, Android/Kotlin, React Native, Unity and Unreal, and maintains an explicit agent-facing surface: an llms.txt index, a hosted documentation MCP server and two published agent skills.

**Areas:** Company · Payments · Checkout · E-Commerce · Fintech · Subscription · Tokenization · Fraud Prevention · Identity · Webhook

## Bolt Financial on APIs.io

Everything profiled for Bolt Financial is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/bolt-financial/](https://apis.io/providers/bolt-financial/)** — or go straight to one of the APIs or properties below.

### APIs (13)

- [Bolt MCP Servers](https://apis.io/apis/bolt-financial/mcp/) — Bolt exposes two Model Context Protocol surfaces: a hosted documentation MCP server advertised at help.boltapp.com/mcp with search_docs, get_doc_page and…
- [Bolt Financial Account API](https://apis.io/apis/bolt-financial/bolt-financial-account-api/) — Use the Account endpoint to view and manage customer accounts. Perform actions such as creating an account, updating an address, or adding a payment method.…
- [Bolt Financial Callbacks API](https://apis.io/apis/bolt-financial/bolt-financial-callbacks-api/) — Implement Callback endpoints on your servers to power Bolt experiences. Different Bolt packages require different callbacks to be implemented. Consult your…
- [Bolt Financial Configuration API](https://apis.io/apis/bolt-financial/bolt-financial-configuration-api/) — Use this resource to retrieve and set Merchant Callback URLs. Bolt uses these URLs to exchange information with your commerce server. See our related guide…
- [Bolt Financial Orders API](https://apis.io/apis/bolt-financial/bolt-financial-orders-api/) — Use the Orders API to interact with the customer's cart throughout the checkout process. Pre-checkout, perform actions such as validating inventory,…
- [Bolt Financial Payments API](https://apis.io/apis/bolt-financial/bolt-financial-payments-api/) — Use the Payments API to process credit card and alternative payment methods with Bolt.
- [Bolt Financial Statements API](https://apis.io/apis/bolt-financial/bolt-financial-statements-api/) — [Statements](/merchants/references/financials/statements/) are available in the Merchant Dashboard for merchants who use Bolt Payments as their processor.…
- [Bolt Financial Subscriptions API](https://apis.io/apis/bolt-financial/bolt-financial-subscriptions-api/) — Use the Subscriptions endpoint to manage merchant-side recurring subscriptions created through Bolt Charge: list and retrieve subscriptions, cancel or…
- [Bolt Financial Testing API](https://apis.io/apis/bolt-financial/bolt-financial-testing-api/) — The testing endpoint allows you to test various functionality within Bolt. Create a test credit card to process a test payment in your store. You can also…
- [Bolt Financial Tokenizer API](https://apis.io/apis/bolt-financial/bolt-financial-tokenizer-api/) — The Tokenizer API from Bolt Financial — 2 operation(s) for tokenizer.
- [Bolt Financial Transactions API](https://apis.io/apis/bolt-financial/bolt-financial-transactions-api/) — Use the Transactions endpoint to authorize payments when the shopper checks out and handle post authorization actions such as captures and refunds. You can…
- [Bolt Financial Webhooks API](https://apis.io/apis/bolt-financial/bolt-financial-webhooks-api/) — Set up webhooks to notify your backend of events within Bolt. These webhooks can communicate with your OMS or other systems to keep them up to date with…
- [Bolt Financial O Auth API](https://apis.io/apis/bolt-financial/bolt-financial-oauth-api/) — Use this endpoint to retrieve an OAuth token. Use the token to allow your ecommerce server to make calls to the Account endpoint and create a one-click…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Bolt Financial Webhooks](https://apis.io/asyncapis/bolt-financial/bolt-financial-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [bolt-financial-mcp.yml](https://apis.io/servers/bolt-financial/bolt-financial-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Bolt Financial Agentic Access](https://apis.io/agentic-access/bolt-financial/bolt-financial-agentic-access/)

#### Collections (4)

Postman and Open Collection request collections.

- [Bolt API Reference](https://apis.io/collections/bolt-financial/open-bolt-financial-bolt-api/)
- [Embedded API Reference](https://apis.io/collections/bolt-financial/open-bolt-financial-embeddable-checkout-v1/)
- [Bolt API Reference](https://apis.io/collections/bolt-financial/open-bolt-financial-embeddable-checkout-v3/)
- [Tokenizer Endpoint](https://apis.io/collections/bolt-financial/open-bolt-financial-tokenizer/)

#### Overlays (4)

OpenAPI overlays, including conversational phrasing for each operation.

- [Bolt Financial Bolt Api Overlay](https://apis.io/overlays/bolt-financial/bolt-financial-bolt-api-overlay/)
- [Bolt Financial Embeddable Checkout V1 Overlay](https://apis.io/overlays/bolt-financial/bolt-financial-embeddable-checkout-v1-overlay/)
- [Bolt Financial Embeddable Checkout V3 Overlay](https://apis.io/overlays/bolt-financial/bolt-financial-embeddable-checkout-v3-overlay/)
- [Bolt Financial Tokenizer Overlay](https://apis.io/overlays/bolt-financial/bolt-financial-tokenizer-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Bolt Financial Authentication](https://apis.io/security/bolt-financial/bolt-financial-authentication/)
- [Bolt Financial Domain Security](https://apis.io/security/bolt-financial/bolt-financial-domain-security/)
- [Bolt Financial Trust Center](https://apis.io/security/bolt-financial/bolt-financial-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Bolt Financial Scopes](https://apis.io/scopes/bolt-financial/bolt-financial-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Bolt Financial Plans Pricing](https://apis.io/plans/bolt-financial/bolt-financial-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Bolt Financial Rate Limits](https://apis.io/rate-limits/bolt-financial/bolt-financial-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Bolt Financial Finops](https://apis.io/finops/bolt-financial/bolt-financial-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.bolt.com)
- [Documentation](https://help.boltapp.com/)
- [Getting started](https://help.boltapp.com/getting-started/introduction/)
- [API reference](https://help.boltapp.com/api-bolt/)
- [Pricing](https://help.boltapp.com/dashboard/billing/fees/)
- [Sign up](https://merchant.boltapp.com/onboarding)
- [Support](https://help.boltapp.com/support)
- [Blog](https://boltapp.com/blog)
- [Terms of service](https://boltapp.com/end-user-terms)
- [Privacy policy](https://boltapp.com/privacy)
- [GitHub](https://github.com/BoltApp)
- [Status](https://status.bolt.com)

## API Evangelist rating

**Kin Score 60.7** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 78.6 |
| Contract quality | 57.5 |
| Contract governance | 18.2 |
| Operational transparency | 42.1 |
| Developer ergonomics | 79.8 |
| Access clarity | 42.1 |

**Agent readiness 50.5** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | documented (partial credit) |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | verified |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | mostly |

**Regulatory alignment 44.6** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/bolt-financial/](https://apis.io/providers/bolt-financial/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Bolt Financial: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/bolt-financial/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
