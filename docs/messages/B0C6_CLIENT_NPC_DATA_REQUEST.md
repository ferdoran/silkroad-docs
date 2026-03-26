# CLIENT_NPC_DATA_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0C6` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A6650` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byRequestType` | `u32` | 4 | `0x009A19AA` |
| 2 | `dwField_02` | `u32` | 4 | `0x009A19B8` |
| 3 | `dwField_03` | `u32` | 4 | `0x009A1AB6` |
| 4 | `dwField_04` | `u32` | 4 | `0x009A1AC4` |
| 5 | `ullField_05` | `u64` | 8 | `0x009A1ADA` |
| 6 | `byField_06` | `u8` | 1 | `0x009A1AE8` |
| 7 | `wField_07` | `u16` | 2 | `0x009A1AF6` |
| 8 | `dwField_08` | `u32` | 4 | `0x009A1B69` |
| 9 | `byField_09` | `u8` | 1 | `0x009A1BB2` |
| 10 | `byField_10` | `u8` | 1 | `0x009A1CB3` |
| 11 | `byField_11` | `u8` | 1 | `0x009A1CCE` |
| 12 | `dwField_12` | `u32` | 4 | `0x009A1D12` |
| 13 | `byField_13` | `u8` | 1 | `0x009A1D41` |

**Total size**: 39 bytes

### Structure Summary

```
  [   0] byRequestType                  u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] ullField_05                    u64
  [  24] byField_06                     u8
  [  25] wField_07                      u16
  [  27] dwField_08                     u32
  [  31] byField_09                     u8
  [  32] byField_10                     u8
  [  33] byField_11                     u8
  [  34] dwField_12                     u32
  [  38] byField_13                     u8
```
