# Plugin template

This directory is a starter template for first-party plugins vendored in this marketplace.

Use it as a starting point when creating a new plugin under `plugins/`.

## Structure

```text
plugins/my-plugin/
├── README.md
├── .mcp.json                 # optional but common for MCP server integrations
├── .grok-plugin/
│   └── plugin.json          # plugin metadata + optional path overrides
├── skills/
│   └── example/
│       └── SKILL.md
├── commands/
│   └── example.md
├── agents/
│   └── example.md
├── hooks/
│   └── hooks.json           # optional
├── .lsp.json                # optional
└── assets/                  # optional brand assets
```

## Required actions when creating a real plugin

1. Copy this folder to a new plugin directory, e.g. `plugins/my-plugin/`.
2. Update the manifest in `.grok-plugin/plugin.json`.
3. Add or replace the example skill/command/agent files with your actual functionality.
4. Add the plugin to `.grok-plugin/marketplace.json`.
5. Run:
   - `python3 scripts/generate-plugin-index.py`
   - `python3 scripts/validate-catalog.py`
