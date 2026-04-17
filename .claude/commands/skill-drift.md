---
description: Compare local tapkit skills against the upstream jootsing-research/skills repo and report drift. SKILLS ONLY. Read-only.
---

This repo (`tapkit-plugins-codex`) mirrors skills from `jootsing-research/skills`. The two are intended to stay in lockstep for **skills** — only the plugin shell differs (`.codex-plugin/` here vs the upstream repo's packaging). Your job is to surface any skill drift between the two so the user can decide what to mirror over.

## Scope: SKILLS ONLY

**This command compares ONLY the contents of `plugins/tapkit/skills/` (local) against `skills/` (upstream). Nothing else.** Do not look at, diff, or report on:

- `.mcp.json` / MCP server config
- `.codex-plugin/plugin.json` or any plugin shell files
- `assets/` (logos, images)
- `README.md`, `TODO.md`, or any top-level files
- `.agents/`, `.claude/`, or any other directories outside the skills trees

Even if you notice drift in those other places while working, **do not mention it**. The user only wants to mirror skills. If they want a broader sync later, they will ask for it explicitly.

This command is **read-only**. Do not edit, add, or delete any files. Only report.

## Steps

1. **Inventory both sides.**
   - Local skills: every directory under `plugins/tapkit/skills/` (each contains a `SKILL.md`).
   - Upstream skills: list `skills/` on `main` of `jootsing-research/skills`:
     ```
     gh api repos/jootsing-research/skills/contents/skills?ref=main --jq '.[] | select(.type=="dir") | .name'
     ```

2. **Compare inventories.** Identify:
   - Skills present **upstream but missing locally** → likely need to be added here.
   - Skills present **locally but missing upstream** → unexpected drift; flag for review.

3. **Diff each shared skill's `SKILL.md`.** For every skill that exists in both, fetch the upstream contents and diff against the local file. Use parallel WebFetch calls for the raw URLs to keep this fast:
   `https://raw.githubusercontent.com/jootsing-research/skills/main/skills/<skill>/SKILL.md`
   Then read the local file at `plugins/tapkit/skills/<skill>/SKILL.md` and compare.

   For each diff, **summarize what changed** — do not dump full file contents. Classify each change as one of:
   - **Mirror** — content change that should be copied over (e.g. new instructions, updated workflow steps, fixed typo, new tips/gotchas).
   - **Adapt** — upstream-specific reference that needs translation for Codex (e.g. mentions of a different plugin shell, Claude/other-host tool names, non-Codex frontmatter conventions).
   - **Ignore** — already correct difference between the two mirrors (the Codex side intentionally diverges here).

4. **Report.** Output one summary with these sections:
   - **Missing locally** — skills upstream that should be added here (bullet list).
   - **Extra locally** — skills here that aren't upstream (bullet list, or "none").
   - **In sync** — skills whose `SKILL.md` matches byte-for-byte (just count + names on one line).
   - **Drifted** — per-skill bullets, each with: skill name, 1–3 line summary of what differs, and the classification (mirror / adapt / ignore) plus a one-line recommendation.

5. **Stop there.** Do not propose a patch unless the user asks for one after seeing the report.
