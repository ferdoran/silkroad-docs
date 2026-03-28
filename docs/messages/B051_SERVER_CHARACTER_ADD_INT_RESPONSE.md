# SERVER_CHARACTER_ADD_INT_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHAT_CLEAR` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB051` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880AC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00880ACE` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```
