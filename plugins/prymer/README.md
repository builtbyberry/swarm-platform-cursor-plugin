# Prymer — Cursor plugin

Connects this project to Prymer, the shared context bus, and teaches Cursor the ritual: load context at the start of a task, checkpoint at the end.

## What is inside

- `mcp.json` — connects the hosted Prymer MCP server at `https://swarmplatform.cloud/mcp/prymer` (browser sign-in on install; no token to copy).
- `rules/prymer.mdc` — the always-applied project rule carrying the ritual. Cursor plugins bundle rules, not a `SessionStart` hook, because Cursor's hook context-injection does not currently reach the agent.
- `skills/prymer/` — the Prymer skill: how to use the tools well (loading, checkpointing, curation, and handoffs).

## Install

Cursor also scans ~/.cursor/plugins/local on startup for locally-installed plugins: copy the unzipped prymer folder to ~/.cursor/plugins/local/prymer, then restart Cursor (or run "Developer: Reload Window").

Or push this extracted folder to a git repo you control, then in Cursor go to Dashboard → Settings → Plugins → Team Marketplaces → Import and paste that repo's URL. Then install the `prymer` plugin from the imported marketplace.

On install, Cursor opens Prymer in your browser to authorize — no token to copy.

## After install

Ask the plugin to onboard this project to Prymer (or, if your Cursor client surfaces MCP prompts, run `onboard-project`) to bind this project to a channel — this bundle has no channel baked in unless you downloaded a channel-pinned copy, so onboarding (or hand-adding a `<!-- prymer-channel: <workspace-slug>/<channel-key> -->` line to a `.cursor/rules/*.mdc` file) is what tells future sessions which one to use.

## License

This plugin is licensed under Apache-2.0 (see `LICENSE`) — fork and adapt the connector freely. The hosted Prymer service it connects to is governed by its own terms; "Prymer" is a trademark and the licence grants no rights to it.
