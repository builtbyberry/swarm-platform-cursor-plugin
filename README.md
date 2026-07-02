# Swarm — Cursor plugin

The Cursor plugin for [Swarm](https://swarmplatform.cloud), the shared context bus
for AI sessions. Installing it connects Cursor to the hosted Swarm MCP server and
adds the always-applied rule that teaches the ritual: load what other sessions
already know at the start of a task, checkpoint your work at the end.

## Install

In Cursor, go to Dashboard → Settings → Plugins → Team Marketplaces → Import, and
paste this repo:

```
builtbyberry/swarm-platform-cursor-plugin
```

Then install the `swarm` plugin from the imported marketplace. Cursor opens Swarm
in your browser to authorize on install — no token to copy.

Prefer to pin the plugin to a specific channel? Download a personalized copy from
the [Connect page](https://swarmplatform.cloud/connect).

## What's inside

- `plugins/swarm/mcp.json` — connects the hosted Swarm MCP server.
- `plugins/swarm/rules/swarm.mdc` — the always-applied project rule carrying the
  ritual. Cursor plugins bundle rules here, not a `SessionStart` hook, because
  Cursor's hook context-injection does not currently reach the agent.
- `plugins/swarm/skills/swarm/` — the Swarm skill: how to use the tools well
  (loading, checkpointing, curation, and handoffs).

## Generated — do not edit

Everything under `plugins/` and `.cursor-plugin/` is rendered from the Swarm app's
canonical connector by `swarm:publish-plugin cursor`. Hand edits drift from canon
and are pruned or flagged by the publisher's `--check` gate on the next publish;
changes land only through a publisher PR. This README is the one hand-maintained
exception (the repo's landing page).

## License

Apache-2.0 (see `LICENSE`) — fork and adapt the plugin freely. The hosted Swarm
service it connects to is governed by its own terms; "Swarm" is a trademark and
the licence grants no rights to it.
