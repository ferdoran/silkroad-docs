# SERVER_ENTITY_GROUPSPAWN_BEGIN

> **Corrected name** (server RE): Was `SERVER_CHARACTER_NAME_CHECK` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3017` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A6DC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRealTime` | `u32` | 4 | `0x008A6DD9` |
| 2 | `wDay` | `u16` | 2 | `0x008A6DE9` |
| 3 | `byHour` | `u8` | 1 | `0x008A6DF9` |
| 4 | `byMinute` | `u8` | 1 | `0x008A6E09` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwRealTime                     u32
  [   4] wDay                           u16
  [   6] byHour                         u8
  [   7] byMinute                       u8
```
