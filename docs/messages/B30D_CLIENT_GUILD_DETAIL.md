# CLIENT_GUILD_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB30D` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x008A1360` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A1378` |
| 2 | `wField_02` | `u16` | 2 | `0x008A1392` |
| 3 | `byField_03` | `u8` | 1 | `0x008A13A0` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A13C3` |
| 5 | `wField_05` | `u16` | 2 | `0x008A13D1` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] byField_03                     u8
  [   4] dwField_04                     u32
  [   8] wField_05                      u16
```
