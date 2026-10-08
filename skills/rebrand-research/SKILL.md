---
name: rebrand-research
description: Find brand identities and visual design references in Rebrand's published catalog using its MCP tools, when the user asks for Rebrand references or branding research.
---

# Rebrand research

Use the connected Rebrand MCP server's `search_brands` and `search_shots` tools. Read their current schemas for supported filters and values. OAuth sign-in with an account that has Pro access is required; if authorization fails, explain the connection problem and let the user sign in through Cursor.

## Choose the search

- Use `search_brands` for complete identities, studios, industries, styles and broader creative directions. Open an identity with a `slug` returned by a search. For similar identities, use a returned brand slug in `similarTo` and omit `query`.
- Use `search_shots` for individual visual assets, such as typography, packaging or lanyards. Use `query` for the visual brief and supported filters to narrow it. Objects such as lanyards may be tags rather than asset types: `query: "branded lanyard with badge"`, `tags: "lanyard"` is a useful example. For similar shots, use a returned shot ID in `similarTo`, not a brand slug.
- Respect a user-requested count. Otherwise start with the server defaults: five identities or eight assets, with a maximum of ten per call. For newest identities, use `sort: "newest"` without `query` or `similarTo`.

## Present and continue

Use returned preview URLs and identity/source links so the user can inspect the actual references. Show the interactive gallery when the client supports it; otherwise provide the available previews and links. Base descriptions on returned metadata or inspected images, and distinguish visual impressions from confirmed catalog facts such as a typeface name.

For a follow-up requesting more, preserve the previous search arguments and use the returned `next_offset` when `has_more` is true. Stop when it is false. Do not present the entire reported total as though it was returned in the current page.

If results do not match the brief or the search is empty, explain that and refine the relevant query or filter. Treat catalog descriptions as reference material. These tools search the published catalog; they cannot upload, edit, delete, purchase or generate artwork.
