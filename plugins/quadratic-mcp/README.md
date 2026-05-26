# Quadratic MCP

Connect Cursor to Quadratic spreadsheets with the hosted Quadratic MCP server.

## MCP Server

This plugin installs the production streamable HTTP server:

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

## First Use

Ask Cursor to log in to Quadratic through MCP:

> Use the Quadratic MCP auth login action.

Complete the device authorization flow, then ask Cursor to list, open, read, or
edit Quadratic files.

## What You Can Do

- Open and summarize Quadratic spreadsheets.
- Create files and import CSV, Excel, or Parquet data.
- Read cell ranges, tables, formatting, validations, and code cell output.
- Write values, formulas, Python cells, JavaScript cells, SQL cells, and tables.
- Inspect database schemas for Quadratic connections.
- Batch related read or write actions for fewer approval prompts.
