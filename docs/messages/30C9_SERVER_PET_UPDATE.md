# SERVER_PET_UPDATE

> **Corrected name** (server RE): Was `SERVER_EXCHANGE_CONFIRM` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30C9` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7A70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7A7E` |
| 2 | `wValue` | `u16` | 2 | `0x008A7A93` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wValue                         u16
```
