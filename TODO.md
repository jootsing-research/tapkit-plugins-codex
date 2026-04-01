# Tap Kit Codex Plugin TODO

## Branding and Metadata

- Add at least one screenshot under `plugins/tapkit/assets/`
- Confirm final marketplace display name and plugin copy
- Add privacy policy and terms of service URLs

## Skill Quality

- Expand each app skill from this condensed first pass into a fuller UI manual
- Audit every text-entry workflow so all skills consistently use the TapKit clipboard-and-paste flow
- Add higher-confidence notes for app versions that move tabs or hide navigation chrome
- Add more example prompts tuned for Codex plugin surfaces

## Validation

- Restart Codex and verify the repo-local marketplace is discovered
- Install the `tapkit` plugin from the local marketplace and confirm the manifest renders cleanly
- Smoke-test MCP connectivity against `https://mcp.tapkit.ai/mcp`
- Run a small end-to-end workflow such as `screenshot`, `open_app`, and one app-specific task

## Expansion

- Decide whether future plugins should stay in one marketplace or be split by product area
- Add more TapKit-oriented plugins once the marketplace shape is stable
- Consider adding helper apps or hooks if TapKit workflows need extra setup or auth guidance
