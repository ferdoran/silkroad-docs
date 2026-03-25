# CLIENT_ENTITY_FULL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB0F3` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881890` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088189E` |
| 2 | `dwField_02` | `u32` | 4 | `0x00996687` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `byField_05` | `u8` | 1 | `0x009966A4` |
| 6 | `dwField_06` | `u32` | 4 | `0x009966B2` |
| 7 | `dwField_07` | `u32` | 4 | `0x0099672B` |
| 8 | `byField_08` | `u8` | 1 | `0x00996739` |
| 9 | `byField_09` | `u8` | 1 | `0x00996747` |
| 10 | `dwField_10` | `u32` | 4 | `0x0099680A` |
| 11 | `wField_11` | `u16` | 2 | `0x00996818` |
| 12 | `bytesData_11` | `bytes` | variable | `0x0099686C` |
| 13 | `byField_13` | `u8` | 1 | `0x0099687A` |
| 14 | `byField_14` | `u8` | 1 | `0x00996888` |
| 15 | `dwField_15` | `u32` | 4 | `0x00996896` |
| 16 | `dwField_16` | `u32` | 4 | `0x009968A4` |
| 17 | `dwField_17` | `u32` | 4 | `0x009968B2` |
| 18 | `dwField_18` | `u32` | 4 | `0x009968C0` |
| 19 | `dwField_19` | `u32` | 4 | `0x009968CE` |
| 20 | `wField_20` | `u16` | 2 | `0x009968DC` |
| 21 | `bytesData_20` | `bytes` | variable | `0x0099691E` |
| 22 | `dwField_22` | `u32` | 4 | `0x0099692C` |
| 23 | `byField_23` | `u8` | 1 | `0x0099693A` |
| 24 | `byField_24` | `u8` | 1 | `0x00996948` |
| 25 | `byField_25` | `u8` | 1 | `0x00996A8F` |
| 26 | `dwField_26` | `u32` | 4 | `0x00996AA9` |
| 27 | `byField_27` | `u8` | 1 | `0x00996AB7` |
| 28 | `dwField_28` | `u32` | 4 | `0x00996AC5` |

**Minimum size**: 64 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] byField_05                     u8
  [   1] dwField_06                     u32
  [   5] dwField_07                     u32
  [   9] byField_08                     u8
  [  10] byField_09                     u8
  [  11] dwField_10                     u32
  [  15] wField_11                      u16
  [  17] bytesData_11                   bytes  (variable length)
  [   0] byField_13                     u8
  [   1] byField_14                     u8
  [   2] dwField_15                     u32
  [   6] dwField_16                     u32
  [  10] dwField_17                     u32
  [  14] dwField_18                     u32
  [  18] dwField_19                     u32
  [  22] wField_20                      u16
  [  24] bytesData_20                   bytes  (variable length)
  [   0] dwField_22                     u32
  [   4] byField_23                     u8
  [   5] byField_24                     u8
  [   6] byField_25                     u8
  [   7] dwField_26                     u32
  [  11] byField_27                     u8
  [  12] dwField_28                     u32
```
