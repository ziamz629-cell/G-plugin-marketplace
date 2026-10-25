# Integration checklist

Use this checklist when adding or updating a marketplace plugin.

## Required catalog metadata
- Add a plugin entry to `.grok-plugin/marketplace.json`
- Use a unique kebab-case `name`
- Include a `source` block
- For remote sources, include a full 40-character lowercase commit `sha`
- Add `description` and `category` when appropriate
- Add `homepage`, `keywords`, and `domains` as needed

## Required plugin structure
For local plugins, ensure the plugin root contains the expected component files:
- `skills/` when skills are provided
- `commands/` when commands are provided
- `agents/` when agents are provided
- `hooks/hooks.json` when lifecycle hooks are used
- `.mcp.json` when MCP server config is used
- `.lsp.json` when LSP config is used
- `.grok-plugin/plugin.json` when a plugin manifest is required

## Validation
Run these commands before opening a PR:

```bash
python3 scripts/generate-plugin-index.py
python3 scripts/validate-catalog.py
```

The CI workflow runs equivalent checks in `.github/workflows/validate-catalog.yml`.

## Integration requirements for future additions
- Keep plugin ownership clear: first-party plugins under `plugins/`, third-party under `external_plugins/`
- Keep sources deterministic and inspectable
- Prefer explicit commit pinning for remote integrations
- Regenerate `.grok-plugin/plugin-index.json` whenever plugin contents change
- Review licensing, README quality, auth flows, and network requirements for any externally hosted plugin
