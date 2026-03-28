# SERVER_ENTITY_GROUPSPAWN_DATA

> **Corrected name** (server RE): Was `SERVER_CHARACTER_LOBBY_INFO` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3019` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008AC0E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byListSub` | `u8` | 1 | `0x008AC0F2` |
| 2 | `wCount` | `u16` | 2 | `0x008AC100` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byListSub                      u8
  [   1] wCount                         u16
```
