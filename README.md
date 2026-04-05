# Tap Kit Plugins for Codex

This repository is a repo-local Codex plugin marketplace for TapKit.

The first plugin is `tapkit`, which connects Codex to a physical iPhone through the TapKit MCP server and ships a reusable skill set for common iOS apps and workflows.

## Current Distribution Status

As of March 31, 2026, the OpenAI Codex plugin docs describe:

- repo-local marketplaces at `$REPO_ROOT/.agents/plugins/marketplace.json`
- personal marketplaces at `~/.agents/plugins/marketplace.json`
- an official Plugin Directory powered by a curated marketplace

This repository includes a repo-local marketplace for development, but the currently verified install flow is a manual personal-marketplace setup after cloning the repo.

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

### Install After Cloning

Codex doesn't officially support community plugins yet — only personal plugins you install yourself. The TapKit plugin is open source and ready to install, you just need to add it manually.

1. Clone this repository to a location of your choice. Remember where you clone it — you'll need the path in the next step.
2. Create the marketplace file at `~/.agents/plugins/marketplace.json`:

```json
{
  "name": "tapkit",
  "interface": {
    "displayName": "Tap Kit"
  },
  "plugins": [
    {
      "name": "tapkit",
      "source": {
        "source": "local",
        "path": "<path-to-cloned-repo>/plugins/tapkit"
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

> **Update the path!** Replace `<path-to-cloned-repo>` with the actual path to where you cloned the repo, relative to your home directory. It must point to the `plugins/tapkit` subdirectory inside the cloned repo.
>
> For example, if you cloned to `~/Dev/tapkit-plugins-codex`, the path would be `./Dev/tapkit-plugins-codex/plugins/tapkit`.

3. **Install the plugin** — restart Codex, then run `/plugin`. Find TapKit in the list and install it.
4. **Authenticate** — once the plugin is loaded, the TapKit MCP server will prompt you to sign in via your browser.
5. **Verify it works:**
   ```
   Take a screenshot of my phone
   ```
   If a phone is connected via the Mac app, you'll see the screenshot.

## Codex Notes

This repo includes a repo-local marketplace at `.agents/plugins/marketplace.json` so it can grow beyond the initial `tapkit` plugin later. For end-user installs, use the personal marketplace at `~/.agents/plugins/marketplace.json` as described above.
