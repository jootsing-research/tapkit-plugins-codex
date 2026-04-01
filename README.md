# Tap Kit Plugins for Codex

This repository is a repo-local Codex plugin marketplace for TapKit.

The first plugin is `tapkit`, which connects Codex to a physical iPhone through the TapKit MCP server and ships a reusable skill set for common iOS apps and workflows.

## Current Distribution Status

As of March 31, 2026, the OpenAI Codex plugin docs describe:

- repo-local marketplaces at `$REPO_ROOT/.agents/plugins/marketplace.json`
- personal marketplaces at `~/.agents/plugins/marketplace.json`
- an official Plugin Directory powered by a curated marketplace

This repository is set up for the repo-local marketplace flow.

The current docs do not describe a self-serve public publishing flow for third-party plugin marketplaces in the way app stores or package registries usually do. In practice, this means this repo is currently structured for local or curated distribution rather than a documented public self-serve Codex marketplace publish path.

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

## Codex Notes

Codex plugin docs recommend a repo-local marketplace at `.agents/plugins/marketplace.json` for curated plugin lists. This repo follows that layout so it can grow beyond the initial `tapkit` plugin later.

The current marketplace entry uses:

- `policy.installation: AVAILABLE`
- `policy.authentication: ON_INSTALL`

The plugin manifest now includes the provided Tap Kit PNG logo asset. Screenshots, privacy-policy links, and terms links are still pending.
