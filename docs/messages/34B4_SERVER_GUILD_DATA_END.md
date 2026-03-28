# SERVER_GUILD_DATA_END

> **Corrected name** (server RE): Was `SERVER_EVENT_DATA` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B4` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x00883060` |

### Fields

No fields could be extracted from this handler. The message may:
- Have no payload (header-only)
- Use an indirect/virtual dispatch that couldn't be traced
- Read data through a mechanism not yet identified
