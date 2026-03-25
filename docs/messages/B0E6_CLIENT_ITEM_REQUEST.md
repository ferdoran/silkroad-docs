# CLIENT_ITEM_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0E6` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008830F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00883121` |
| 2 | `byField_02` | `u8` | 1 | `0x0088313B` |
| 3 | `dwField_03` | `u32` | 4 | `0x00883149` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
```
