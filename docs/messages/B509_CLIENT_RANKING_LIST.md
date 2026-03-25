# CLIENT_RANKING_LIST

| Property | Value |
|----------|-------|
| Opcode | `0xB509` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x008A31D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A321B` |
| 2 | `byField_02` | `u8` | 1 | `0x008A3242` |
| 3 | `byField_03` | `u8` | 1 | `0x008A3292` |
| 4 | `byField_04` | `u8` | 1 | `0x008A32A0` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A32AE` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A32BC` |
| 7 | `ullField_07` | `u64` | 8 | `0x008A32CA` |
| 8 | `ullField_08` | `u64` | 8 | `0x008A32D8` |
| 9 | `dwField_09` | `u32` | 4 | `0x008A32E6` |
| 10 | `wField_10` | `u16` | 2 | `0x008A3422` |

**Total size**: 34 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] ullField_07                    u64
  [  20] ullField_08                    u64
  [  28] dwField_09                     u32
  [  32] wField_10                      u16
```
