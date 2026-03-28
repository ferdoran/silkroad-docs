# SERVER_PARTY_INVITATION_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SIEGE_ACTION` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB060` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00871D50` |

### Fields

No fields could be extracted from this handler. The message may:
- Have no payload (header-only)
- Use an indirect/virtual dispatch that couldn't be traced
- Read data through a mechanism not yet identified
