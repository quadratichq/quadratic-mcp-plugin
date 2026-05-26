# Quadratic MCP Cursor Plugin

This repository packages the hosted Quadratic MCP server as a Cursor plugin.
Installing it connects Cursor to Quadratic spreadsheets through the production
streamable HTTP MCP endpoint:

```json
{
  "mcpServers": {
    "quadratic": {
      "type": "streamable-http",
      "url": "https://mcp.quadratichq.com/mcp"
    }
  }
}
```

## Included

- `plugins/quadratic-mcp/mcp.json` adds the hosted Quadratic MCP server.
- `plugins/quadratic-mcp/rules/` provides light guidance for using Quadratic MCP safely.
- `plugins/quadratic-mcp/skills/` adds an on-demand spreadsheet workflow skill.
- `plugins/quadratic-mcp/assets/logo.svg` is the marketplace logo.

## Usage

After installing the plugin in Cursor, open a chat and ask to work with a
Quadratic spreadsheet. If you are not authenticated yet, ask Cursor to run the
Quadratic MCP `auth` tool with the `login` action and complete the device auth
flow.

Example prompts:

- "Open my Budget 2026 Quadratic file and summarize it."
- "Create a Quadratic spreadsheet from this CSV."
- "Add a Python code cell that analyzes sales by month."
- "Show me the schema for my connected Postgres database."

## Development

Validate the plugin manifest and referenced files:

```bash
node scripts/validate-template.mjs
```

The marketplace manifest lives at `.cursor-plugin/marketplace.json`. The plugin
manifest lives at `plugins/quadratic-mcp/.cursor-plugin/plugin.json`.
