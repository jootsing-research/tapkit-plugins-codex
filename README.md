# TapKit Plugins for Codex

This repository publishes the TapKit Codex plugin marketplace.

The first plugin is `tapkit`, which connects Codex to a physical iPhone through the TapKit MCP server and ships reusable skill guidance for common iOS apps and workflows.

## Installation

Add the marketplace with the Codex CLI:

```sh
codex plugin marketplace add jootsing-research/tapkit-plugins-codex
```

Then open the Codex plugin directory, choose the `TapKit Plugins` marketplace, and install the `tapkit` plugin.

To upgrade this marketplace directly:

```sh
codex plugin marketplace upgrade tapkit-plugins
```

To upgrade all configured marketplaces, run:

```sh
codex plugin marketplace upgrade
```

## Requirements

- Codex with plugin marketplace CLI support
- TapKit access through the TapKit MCP server
- A physical iPhone connected through the TapKit Mac app when running phone-control workflows

After installing the plugin, Codex may prompt you to authenticate TapKit in your browser when the MCP server is first used.

## Structure

- `.agents/plugins/marketplace.json`: Codex marketplace entry for this repository
- `plugins/tapkit/.codex-plugin/plugin.json`: TapKit plugin manifest
- `plugins/tapkit/.mcp.json`: TapKit MCP server configuration
- `plugins/tapkit/skills/*/SKILL.md`: bundled skills for phone control and app-specific guidance

## Verify The Install

After installing the `tapkit` plugin, try one of these prompts in Codex:

```text
What phones can you see with TapKit right now?
```

```text
What's on my phone right now?
```

```text
Take a screenshot of my phone
```

If a phone is connected through the TapKit Mac app and TapKit authentication is complete, Codex should be able to inspect or control the device through the TapKit MCP tools.

## Development

This repository includes a repo-local marketplace at `.agents/plugins/marketplace.json` so contributors can test plugin changes from a checkout.

Use this flow when you want Codex to load the marketplace directly from this repo:

1. Open this repository in Codex.
2. Confirm the repo-local marketplace file exists at `.agents/plugins/marketplace.json`.
3. Confirm the plugin directory exists at `plugins/tapkit/`.
4. Restart Codex so it re-reads the local marketplace.
5. Open the plugin directory UI and look for the marketplace `TapKit Plugins`.
6. Install the `tapkit` plugin from that marketplace.
7. Test with one of the verification prompts above.

When you change plugin files in this repo, restart Codex again so the local install picks up the updated files.
