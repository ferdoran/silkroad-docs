# SERVER_GUILD_DATA_BEGIN

> **Corrected name** (server RE): Was `SERVER_EVENT_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34B3` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x00881C60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881C6E` |
| 2 | `wField_02` | `u16` | 2 | `0x00881C88` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
