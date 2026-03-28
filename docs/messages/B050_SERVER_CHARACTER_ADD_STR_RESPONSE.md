# SERVER_CHARACTER_ADD_STR_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_CHAT_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB050` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087FFD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byChatType` | `u8` | 1 | `0x0087FFDE` |
| 2 | `wMessageLen` | `u16` | 2 | `0x0087FFF8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byChatType                     u8
  [   1] wMessageLen                    u16
```
