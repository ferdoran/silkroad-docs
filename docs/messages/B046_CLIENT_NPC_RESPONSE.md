# CLIENT_NPC_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0xB046` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00882E50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00882E75` |
| 2 | `byField_02` | `u8` | 1 | `0x00882E83` |
| 3 | `dwField_03` | `u32` | 4 | `0x00882E91` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
```
