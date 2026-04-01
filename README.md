# Tap Kit Plugins for Codex

This repository is a repo-local Codex plugin marketplace for TapKit.

The first plugin is `tapkit`, which connects Codex to a physical iPhone through the TapKit MCP server and ships a reusable skill set for common iOS apps and workflows.

## Current Distribution Status

As of March 31, 2026, the OpenAI Codex plugin docs describe:

- repo-local marketplaces at `$REPO_ROOT/.agents/plugins/marketplace.json`
- personal marketplaces at `~/.agents/plugins/marketplace.json`
- an official Plugin Directory powered by a curated marketplace

This repository is set up for the repo-local marketplace flow.

As of March 31, 2026, the current docs describe local testing and a curated official Plugin Directory, but they do not document a self-serve public publishing path for third-party plugin marketplaces. In practice, this repo is currently structured for local or curated distribution.

## Structure

- `.agents/plugins/marketplace.json`: repo-local marketplace entry that Codex can discover
- `plugins/tapkit/.codex-plugin/plugin.json`: Tap Kit plugin manifest
- `plugins/tapkit/.mcp.json`: TapKit MCP server configuration
- `plugins/tapkit/skills/*/SKILL.md`: bundled skills for phone control and app-specific guidance

## Current Scope

This first pass mirrors the same high-level capability set as the sibling Claude plugin:

- Core TapKit iPhone control
- Clock
- Facebook
- Hinge
- Instagram
- LinkedIn
- Telegram
- TikTok
- Twitter / X
- Uber Eats
- Weather

The app skills here are intentionally concise. They are meant to be usable in Codex immediately while leaving room for a second pass that expands each one into a more exhaustive app manual.

## Testing

### Test Inside This Repo

Use this flow when you want Codex to load the marketplace directly from this checkout.

1. Open this repository in Codex.
2. Confirm the repo-local marketplace file exists at `.agents/plugins/marketplace.json`.
3. Confirm the plugin directory exists at `plugins/tapkit/`.
4. Restart Codex so it re-reads the local marketplace.
5. Open the plugin directory UI and look for the marketplace `Tap Kit Plugins`.
6. Install the `tapkit` plugin from that marketplace.
7. Test with the default prompts:
   - `What phones can you see with TapKit right now?`
   - `What's on my phone right now?`

When you change plugin files in this repo, restart Codex again so the local install picks up the updated files.

### Test Outside This Repo

Use this flow when you want to test the plugin from your personal Codex marketplace instead of from this repository.

1. Copy the plugin folder into your Codex plugin area:

```bash
mkdir -p ~/.codex/plugins
cp -R /absolute/path/to/tapkit-plugins-codex/plugins/tapkit ~/.codex/plugins/tapkit
```

2. Create or update your personal marketplace at `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "tapkit-local",
  "interface": {
    "displayName": "Tap Kit Local"
  },
  "plugins": [
    {
      "name": "tapkit",
      "source": {
        "source": "local",
        "path": "./.codex/plugins/tapkit"
      },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

3. Restart Codex.
4. Open the plugin directory UI.
5. Find the marketplace `Tap Kit Local`.
6. Install `tapkit`.
7. Run the same default prompts to verify that TapKit can enumerate devices and inspect the current phone screen.

If you update the plugin later, copy the plugin folder again to `~/.codex/plugins/tapkit` and restart Codex.

## Codex Notes

Codex plugin docs recommend a repo-local marketplace at `.agents/plugins/marketplace.json` for curated plugin lists. This repo follows that layout so it can grow beyond the initial `tapkit` plugin later.

For personal testing outside a repository, Codex also supports `~/.agents/plugins/marketplace.json`. The `source.path` value is resolved relative to the marketplace root, not relative to the `.agents/plugins/` directory.

The current marketplace entry uses:

- `policy.installation: AVAILABLE`
- `policy.authentication: ON_INSTALL`

The plugin manifest now includes the provided Tap Kit PNG logo asset. Screenshots, privacy-policy links, and terms links are still pending.
