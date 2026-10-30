# VibeVO connection package

Connect supported VibeVO account data and workflows to Cursor. This repository contains public connection metadata, documentation and VibeVO brand assets. The hosted service is provided by VibeVO; its application/server source is not part of this package.

## Status

This package is prepared for marketplace review. Source-package validation is separate from live OAuth connection tests and catalogue approval. No marketplace approval or automatic installation from a chat message is claimed.

## What it connects

- Available campaign summaries, posts, creator statistics and tracking information.
- Creator posts and social accounts.
- Content-factory summaries, monitored accounts and posts.
- Your own wallet balance and transaction history.
- Unfunded campaign drafts and permitted profile, publishing, reporting and account-access workflows.

The default configuration requests **read** access. Supported changes require separately requested **write** consent, current account permissions and feature access. The hosted connection currently offers 237 tools across these scopes. Monitoring can maintain or consume existing included or previously purchased nonwithdrawable monitoring credits; it cannot purchase new credits.

The hosted connection cannot request or cancel withdrawals, initiate transfers or top-ups, create payment-provider orders or quotes, purchase credits, trade accounts, launch or change the lifecycle of campaigns, run funded placement workflows, submit quizzes for monetary rewards, or start/rerun AI image or video generation and generative edits. Historical balances and transactions remain available for display. Supported text translation and deterministic overlay previews remain available.

Reads default to the connected owner's account. For tools accepting `accountId`, first list accessible accounts and explicitly select an authorized account. Selecting a shared account in the browser cabinet does not select it in the connector. Roles, scopes and object permissions are checked by VibeVO. Some cabinet screens and charts have no tool; this connection does not provide complete cabinet parity or read local server files.

## Connect in Cursor

The Cursor manifest is `.cursor-plugin/plugin.json` and selects `mcp.json`. The configuration contains the public OAuth client identifier `vibevo-cursor`; this is not a secret.

After installing this package through a supported Cursor plugin installation flow, enable the VibeVO MCP server, sign in to VibeVO in the browser and review the account and permissions. Do not send API keys in chat.

The configuration can also be added through Cursor's ordinary MCP settings:

```json
{
  "mcpServers": {
    "vibevo": {
      "url": "https://api.vibevo.io/api/v1/mcp",
      "auth": { "CLIENT_ID": "vibevo-cursor", "scopes": ["read"] }
    }
  }
}
```

To use supported writes, explicitly request both `read` and `write`, reconnect and review the new consent. `mcp.write.example.json` shows that optional configuration; the manifest does not activate it automatically. Preserve other existing MCP entries when adjusting a personal configuration.

## ChatGPT and Claude

This repository is a Cursor plugin package only. It does not contain an OpenAI/Codex or Claude plugin manifest.

The VibeVO hosted URL can also be added manually as a custom connector in supported ChatGPT and Claude clients, followed by VibeVO account sign-in and consent. Use the platform-specific setup documentation linked below. Directory listings and approval are separate applications; this package does not establish them. Native coding clients may use different OAuth callbacks and require their own explicitly supported setup.

## Example requests

- “List my VibeVO campaigns and summarize the available statistics.”
- “Show my content-factory statistics without running a scan.”
- “Show my VibeVO wallet balance and the first page of transactions.”

Use IDs returned by the connected account, clarify the intended factory/campaign and period, and preserve unavailable measurements as unknown. A statistics request should not trigger purchases or paid refreshes.

## Account and fees

A VibeVO account and access to the relevant records/features are required. This connection-metadata package has no separate purchase price. VibeVO service charges and monitoring usage follow the account's existing product terms. This hosted connection cannot purchase credits or initiate payment and withdrawal operations. The package licence does not waive those service charges or establish marketplace-policy eligibility.

Revoke the corresponding connection key in VibeVO settings to remove its access. Do not commit credentials, tokens, reviewer accounts or private records to this repository.

## Links

- [Product](https://vibevo.io)
- [Setup documentation](https://docs.vibevo.io/docs/en/api/mcp)
- [Support](https://docs.vibevo.io/docs/en/support)
- [Privacy policy](https://advertiser.vibevo.io/privacy)
- [Terms](https://advertiser.vibevo.io/terms)

## Licence

Package metadata and documentation are provided under the MIT licence. VibeVO names and marks identify the service and remain the property of their owners; the licence does not grant a right to imply endorsement of another service.
