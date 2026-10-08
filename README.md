# Rebrand

Search Rebrand's published brand identities and visual assets from an MCP client.

## Capabilities

- `search_brands`: search identities, filter the catalog, open a returned slug and find similar brands.
- `search_shots`: search individual visual assets by description, asset type, tags or color.
- Clients supporting MCP Apps can display an interactive gallery. Other clients receive references and source links.

## Connection

Remote Streamable HTTP endpoint: `https://mcp.rebrand.gallery/mcp`.
Authenticate through Rebrand's OAuth sign-in and consent flow using an existing account with access to the feature.
No API keys or passwords belong in the configuration.

## Limits

The tools read the published catalog. They do not edit, delete, upload or generate artwork.
Results depend on the current catalog; empty searches should not be presented as successful matches.

## Documentation, privacy and support

- Setup: https://mcp.rebrand.gallery
- Privacy: https://www.rebrand.gallery/privacy-policy
- Terms: https://www.rebrand.gallery/terms
- Support: contact@rebrand.gallery

Rebrand authenticates the account and checks feature entitlement. Search arguments and sanitized product telemetry are handled as described in the privacy policy. This configuration package includes no credentials or user data.

## Cursor plugin

This package includes the Rebrand MCP connection and the `rebrand-research` skill for finding visual references, opening identities and continuing a search. It contains no executable scripts, hooks or application source.

A Rebrand account with active Pro access is required. After installation, complete OAuth in Cursor.

### Try the MCP connection

[Add Rebrand MCP to Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=rebrand&config=eyJ1cmwiOiJodHRwczovL21jcC5yZWJyYW5kLmdhbGxlcnkvbWNwIn0%3D)

This link installs the connection only. Install the full plugin to include its research skill.

### Test the full plugin locally

1. Copy this repository's contents, including `.cursor-plugin`, into `~/.cursor/plugins/local/rebrand/`.
2. Run **Developer: Reload Window** in Cursor and open **Customize**. Confirm that the research skill and Rebrand MCP server are discovered.
3. Complete Rebrand OAuth. If Rebrand MCP was already added separately, use one connection to avoid duplicate tools.
4. Ask: “Use Rebrand to find five playful food and beverage brand identities.”
5. Ask: “Show eight branded lanyard designs from Rebrand, with images and links to each identity.” Then ask for the next eight and check that the results differ.

Cursor clients without MCP Apps support may show tool references and image links instead of an interactive gallery.

## License

The plugin configuration, documentation and research skill are MIT licensed. The Rebrand logo and other brand marks are excluded from that license and remain the property of their owners. The hosted service, catalog and referenced artwork are governed by their own terms and rights.
