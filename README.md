# Swarm — Cursor plugin marketplace

The Cursor plugin marketplace for [Swarm](https://swarmplatform.cloud), the shared context bus. Installing the `swarm` plugin connects the hosted Swarm MCP server and adds the always-applied project rule that teaches the load-at-start / checkpoint-at-end ritual.

## Install

Cursor also scans ~/.cursor/plugins/local on startup for locally-installed plugins: copy the unzipped swarm folder to ~/.cursor/plugins/local/swarm, then restart Cursor (or run "Developer: Reload Window").

Or push this extracted folder to a git repo you control, then in Cursor go to Dashboard → Settings → Plugins → Team Marketplaces → Import and paste that repo's URL. Then install the `swarm` plugin from the imported marketplace.

Cursor opens Swarm in your browser to authorize on install — no token to copy.

Then ask the plugin to onboard this project to Swarm (or, if your Cursor client surfaces MCP prompts, run `onboard-project`) to bind this project to a channel — the marketplace install has no channel baked in, so onboarding (or hand-adding a `<!-- swarm-channel: <workspace-slug>/<channel-key> -->` line to a `.cursor/rules/*.mdc` file) is what tells future sessions which one to use.

## Generated — do not edit

Every file here is rendered from the Swarm app's canonical connector by `swarm:publish-plugin cursor`. Hand edits drift from canon and are pruned or flagged by the publisher's `--check` gate on the next publish; changes land only through a publisher PR.

## License

Apache-2.0 (see `LICENSE`) — fork and adapt the plugin freely. The hosted Swarm service it connects to is governed by its own terms; "Swarm" is a trademark and the licence grants no rights to it.
