# SERVER_ARENA_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x325D` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00899CF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00899D11` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899D1F` |
| 3 | `dwField_03` | `u32` | 4 | `0x00899D2D` |
| 4 | `byField_04` | `u8` | 1 | `0x00899D3B` |

**Total size**: 13 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] byField_04                     u8
```
