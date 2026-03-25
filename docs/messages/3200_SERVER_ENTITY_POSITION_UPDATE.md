# SERVER_ENTITY_POSITION_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x3200` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x008A5280` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A5291` |
| 2 | `dwPosX` | `u32` | 4 | `0x008A529F` |
| 3 | `dwPosZ` | `u32` | 4 | `0x008A52AD` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwPosX                         u32
  [   8] dwPosZ                         u32
```
