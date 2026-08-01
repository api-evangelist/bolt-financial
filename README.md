# Bolt Financial

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
