# SERVER_ENTITY_UPDATE_STATUS

| Property | Value |
|----------|-------|
| Opcode | `0x304D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880A70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUpdateType` | `u8` | 1 | `0x00880A7E` |
| 2 | `wValue` | `u16` | 2 | `0x00880A93` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byUpdateType                   u8
  [   1] wValue                         u16
```
