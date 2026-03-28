# SERVER_ENVIROMENT_WEATHER_UPDATE

> **Corrected name** (server RE): Was `SERVER_TIME_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3809` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x008A6E80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wDay` | `u16` | 2 | `0x008A6E9E` |
| 2 | `byHour` | `u8` | 1 | `0x008A6EAE` |
| 3 | `byMinute` | `u8` | 1 | `0x008A6EBE` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] wDay                           u16
  [   2] byHour                         u8
  [   3] byMinute                       u8
```
