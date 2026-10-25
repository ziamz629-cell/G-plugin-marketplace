# External plugins

This directory stores vendored third-party plugins or local copies that are referenced by the marketplace catalog.

Rules:
- Create one plugin per subdirectory, for example: `external_plugins/neon/`
- If the plugin is vendored locally, ensure it contains the required component files and an appropriate `.grok-plugin/plugin.json` manifest
- If the plugin is referenced remotely, keep a pinned `sha` in `.grok-plugin/marketplace.json`
- Regenerate the catalog after changes:
  - `python3 scripts/generate-plugin-index.py`
  - `python3 scripts/validate-catalog.py`

This folder is also the right place for locally curated integrations that need source control or offline review before publication.
