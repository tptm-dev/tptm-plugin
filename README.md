# TPTM plugin for Grok Bot and Cursor

Connects the assistant to the TPTM remote MCP server (`https://tptm.pro/mcp`).
Grok Bot's **Connect apps** catalog is
the Cursor Marketplace, so one package serves both.

You need an existing TPTM account. The first time the app is used, your browser
opens TPTM: sign in, pick the organization, choose what the assistant may read or
change, and approve. It can never do more than your own TPTM role allows. Manage or
revoke the connection any time in TPTM → Settings → AI Connectors.

## Install

Once listed: in Grok Bot open **Connect apps**, search for **TPTM**, add it, then
choose **Authorize**. In Cursor, add it from the Marketplace.

## Before it is listed: add TPTM as a custom connector

Grok Bot desktop → **Connect apps** → **Add a custom connector**:

- Name: `TPTM`
- Type: **Remote HTTPS**
- Server URL: `https://tptm.pro/mcp`
- Leave HTTP headers, Client ID and Client Secret empty. TPTM registers the client
  itself (OAuth dynamic client registration).

Choose **Add plugin**, then **Authorize**. You can also ask a Bot: "Add the MCP
server at https://tptm.pro/mcp".

Grok Build (the CLI):

```bash
grok mcp add --transport http tptm https://tptm.pro/mcp
```

## Contents

| Path | What it is |
|---|---|
| `.cursor-plugin/plugin.json` | Manifest |
| `mcp.json` | The one remote MCP server |
| `assets/logo.svg` | Listing logo |
