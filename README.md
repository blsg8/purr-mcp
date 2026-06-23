# purr-mcp

MCP engine for [Purr](https://github.com/blsg8/purrside-app) — read and write your
local Purr notes from AI clients like Claude Code.

The engine is a small, notarized command-line tool that reads Purr's local store
**read/write** on your Mac. Nothing is sent to any server; it runs only when a
client launches it.

## Install (Claude Code — recommended)

```
/plugin marketplace add blsg8/purr-mcp
/plugin install purr@purr-mcp
```

The plugin bundles the notarized engine, so there's nothing else to install — no
Node, no manual config. Restart Claude Code (or `/reload-plugins`) and the `purr`
tools appear.

## Install (other MCP clients)

Clients that don't support Claude Code plugins (Claude Desktop, Codex, etc.) can
either:

1. **Use Purr's in-app installer** — open Purr → Settings → Integrations →
   *MCP Engine* → **Install Engine**. Then copy the registration command shown
   for your client.

2. **Point at the binary manually**. Download `purr-mcp` from the latest
   [release](https://github.com/blsg8/purr-mcp/releases), make it executable,
   and add it to your client's MCP config as a `stdio` server:

   ```json
   {
     "mcpServers": {
       "purr": { "command": "/absolute/path/to/purr-mcp" }
     }
   }
   ```

## Releases

Binaries are universal (Apple silicon + Intel), signed with Developer ID and
notarized by Apple. The tag matches the engine version, e.g. `mcp-v0.1.0`.
