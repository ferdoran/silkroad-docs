# SERVER_GUILD_DATA

> **Corrected name** (server RE): Was `SERVER_NOTICE_CLEAR` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3101` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00883060` |

### Fields

No fields could be extracted from this handler. The message may:
- Have no payload (header-only)
- Use an indirect/virtual dispatch that couldn't be traced
- Read data through a mechanism not yet identified
