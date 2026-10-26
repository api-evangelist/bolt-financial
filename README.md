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

Bolt Financial, Inc. gives retailers a one-click, identity-powered checkout backed by a
shopper account network, payments processing, card tokenization and fraud protection.

- Website: https://www.bolt.com
- Documentation: https://help.boltapp.com/
- Developer resources: https://help.boltapp.com/developers/
- API reference: https://help.boltapp.com/api-bolt/
- GitHub: https://github.com/BoltApp
- Status: https://status.bolt.com

## APIs

| API | Spec | Operations | Base URL |
|---|---|---|---|
| Bolt API | OpenAPI 3.0.0, v1.0.1 | 39 | https://api.boltapp.com |
| Embeddable Checkout v1 | OpenAPI 3.0.0, v1.0.1 | 20 | https://api.boltapp.com |
| Embeddable Checkout v3 | OpenAPI 3.0.0, v3.3.22 | 16 | https://api.boltapp.com/v3 |
| Tokenizer | OpenAPI 3.0.0, v1.0.0 | 2 | https://production.bolttk.com |

## Artifacts

`openapi/` · `overlays/` · `authentication/` · `scopes/` · `conventions/` · `errors/` ·
`lifecycle/` · `sandbox/` · `changelog/` · `components/` · `data-model/` · `conformance/` ·
`asyncapi/` (webhook catalog) · `mcp/` (server + tool crosswalk) · `packages/` ·
`well-known/` · `llms/` · `skills/` · `security/` (domain security)

## Notes

- Bolt maintains a deliberate agent surface: an `llms.txt` index, a hosted documentation MCP
  server, two published agent skills, and a Speakeasy-generated API MCP server with 22 tools.
- Bolt publishes no AsyncAPI document; the webhook catalog was captured from the docs.
- Bolt publishes no A2A agent card, no `security.txt`, and no decline-code reference of its
  own (it defers to the merchant's configured processor).
