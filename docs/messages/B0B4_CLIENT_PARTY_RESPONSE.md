# CLIENT_PARTY_RESPONSE

| Property | Value |
|----------|-------|
| Opcode | `0xB0B4` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872450` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087245F` |
| 2 | `wField_02` | `u16` | 2 | `0x008724C6` |
| 3 | `byField_03` | `u8` | 1 | `0x0087250E` |
| 4 | `byField_04` | `u8` | 1 | `0x00872532` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] byField_03                     u8
  [   4] byField_04                     u8
```
