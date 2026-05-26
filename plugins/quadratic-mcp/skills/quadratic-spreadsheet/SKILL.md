---
name: quadratic-spreadsheet
description: Work with Quadratic spreadsheets through the hosted Quadratic MCP server. Use when the user asks to inspect, create, edit, import, or analyze Quadratic files.
---

# Quadratic Spreadsheet

Use this skill when a task involves Quadratic files, spreadsheet ranges,
formulas, Python or JavaScript code cells, SQL connection cells, imports, or
spreadsheet formatting.

## Workflow

1. Confirm the Quadratic MCP server is available as `quadratic`.
2. If authentication is needed, call `auth` with action `login` and guide the
   user through the device authorization flow.
3. Use `files_read` to list or identify the target file, then `files_write` to
   open it.
4. Start with `read_data` action `get_spreadsheet_context` or `outline` to
   understand sheets, tables, code cells, charts, images, and existing data.
5. Use targeted `read_data` calls for specific ranges or tables. Consolidate
   independent reads with `action: "batch"` when useful.
6. For edits, use `write_data` and place new content outside occupied ranges.
   Leave a blank row or column between new content and existing data.
7. After writes, read back the changed range or context needed to verify the
   result.

## Notes

- Quadratic tables do not support formulas or code cells inside the table.
- Code cells are not global; variables and imports are scoped to each cell.
- Use formatting tools for cell formatting rather than trying to format from
  Python or JavaScript code.
- For table columns, prefer table references such as `TableName[Column]`.
