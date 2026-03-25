# SERVER_ENTITY_HP_MP

| Property | Value |
|----------|-------|
| Opcode | `0x3036` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A9560` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A9594` |
| 2 | `byUpdateType` | `u8` | 1 | `0x008A95A2` |
| 3 | `dwValue` | `u32` | 4 | `0x008A95B0` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byUpdateType                   u8
  [   5] dwValue                        u32
```
