# Standards MCP server

Serves the catalogue to any MCP client, so a system is something an agent queries rather
than a file somebody remembers to paste. Standard library only, like the compiler.

```bash
python3 mcp/server.py --selftest     # exercise the protocol without a client
python3 mcp/server.py                # serve over stdio
```

## Connecting it

```json
{
  "mcpServers": {
    "standards": {
      "command": "python3",
      "args": ["/absolute/path/to/standards/mcp/server.py"]
    }
  }
}
```

Add `"--packs", "/path/to/packs"` to the args to serve a catalogue somewhere else.

## Tools

| Tool | What it does |
|---|---|
| `list_systems` | Every system, with constraint counts, type licence and pack licence. Call first |
| `get_system` | One instruction build — `compact` for small models, `full` for frontier, `reference` on demand |
| `get_tokens` | The token contract as JSON |
| `get_archetypes` | The compositional moves as JSON |
| `select_move` | The move for a rhetorical job — E, S, N, C, T or W, by code or name |

Every pack file is also exposed as a resource under `standards://<system>/<file>`.

## Why a server rather than a download

Two reasons, one practical and one commercial.

**Practical.** `get_tokens` and `get_archetypes` return the JSON contracts rather than making
the model parse them out of prose — measurably fewer tokens and fewer hallucinated values.
And `select_move` implements the selection argument the schema makes: one move is active per
artefact, so an agent should ask for the one it needs rather than load a table of nine and
try to satisfy all of them.

**Commercial.** A markdown ruleset can be pasted anywhere once bought. A server is how this
category installs things, and it is the difference between being a download and being
infrastructure.

## Licensing

The server serves whatever packs are present on disk. It does not enforce entitlement —
`list_systems` reports each pack's licence so a client can see what it is holding, and
Instrument is CC BY 4.0 while the other five are proprietary. Entitlement belongs at
distribution, not here.
