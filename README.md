# Envision-Construction Claude Code Marketplace

Marketplace registry for plugins owned/forked by Envision-Construction.

This repo only contains the marketplace catalog (`.claude-plugin/marketplace.json`). It does NOT host plugin source — each plugin lives in its own repo and is referenced by the `source` field in the catalog.

## Registered plugins

| Plugin | Source | Description |
|---|---|---|
| nano-banana-2 | `Envision-Construction/nano-banana-2-mcp` | Google Gemini Nano Banana 2 image-gen MCP, forked from daveremy/nano-banana-2-mcp |

## Why this exists

Originally `nano-banana-2-plugins` pointed at `daveremy/nano-banana-2-mcp`, where the same repo served as both the marketplace registry AND the plugin source. That made Claude Code read `.claude-plugin/plugin.json`'s `mcpServers` at both layers and emit a dedup warning on every session. Splitting them eliminates the duplicate read path.
