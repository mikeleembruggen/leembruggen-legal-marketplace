# leembruggen-legal plugin marketplace

Claude plugin marketplace. Contains:
- `practice-assistant/`: the Practice Assistant plugin

## Install (customer)
Claude → Customize → Plugins → **Add → Add marketplace** → enter `mikeleembruggen/leembruggen-legal-marketplace`, then install **Practice Assistant**.
Alternatively, upload `practice-assistant.plugin` via **Add → Upload plugin**.

## Release (maintainer)
1. Edit skills under `practice-assistant/skills/`.
2. Bump `version` in `practice-assistant/.claude-plugin/plugin.json`.
3. Rebuild the upload file: `cd practice-assistant && zip -r ../practice-assistant.plugin . -x "*.DS_Store"`
4. Commit and push. Marketplace installs pick up the update on sync.

Never commit client data.
