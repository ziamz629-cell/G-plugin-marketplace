# First-party plugins

This directory is reserved for first-party plugins that are vendored in this repository.

Rules:
- Place each plugin in its own subdirectory under this folder, for example: `plugins/my-plugin/`
- Each plugin should include a valid plugin root with its own manifest and component files when applicable
- Add or update the corresponding catalog entry in `.grok-plugin/marketplace.json`
- Regenerate the component index by running:
  - `python3 scripts/generate-plugin-index.py`
  - `python3 scripts/validate-catalog.py`

If a plugin is not vendored here, prefer a remote source entry in the marketplace catalog instead.
