# SERVER_CHARACTER_DATA

> **Corrected name** (server RE): Was `SERVER_CHARACTER_CREATE_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3013` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6580` |

### Fields

No fields could be extracted from this handler. The message may:
- Have no payload (header-only)
- Use an indirect/virtual dispatch that couldn't be traced
- Read data through a mechanism not yet identified
