# CLIENT_ENTITY_DETAIL_DATA_2

| Property | Value |
|----------|-------|
| Opcode | `0xB0F9` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00887300` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088737B` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088753B` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `byField_05` | `u8` | 1 | `0x00887558` |
| 6 | `byField_06` | `u8` | 1 | `0x00887566` |
| 7 | `dwField_07` | `u32` | 4 | `0x00887574` |
| 8 | `dwField_08` | `u32` | 4 | `0x00887582` |
| 9 | `dwField_09` | `u32` | 4 | `0x00887590` |
| 10 | `dwField_10` | `u32` | 4 | `0x0088759E` |
| 11 | `dwField_11` | `u32` | 4 | `0x008875AC` |
| 12 | `dwField_12` | `u32` | 4 | `0x008875C9` |
| 13 | `byField_13` | `u8` | 1 | `0x008875D7` |
| 14 | `byField_14` | `u8` | 1 | `0x008875E5` |
| 15 | `dwField_15` | `u32` | 4 | `0x00887747` |
| 16 | `byField_16` | `u8` | 1 | `0x00887807` |
| 17 | `dwField_17` | `u32` | 4 | `0x008879DC` |
| 18 | `byField_18` | `u8` | 1 | `0x008879EA` |
| 19 | `byField_19` | `u8` | 1 | `0x005BB24E` |
| 20 | `byField_20` | `u8` | 1 | `0x005BB276` |
| 21 | `byField_21` | `u8` | 1 | `0x005BB683` |
| 22 | `dwField_22` | `u32` | 4 | `0x005BB86D` |
| 23 | `dwField_23` | `u32` | 4 | `0x005BB890` |
| 24 | `byField_24` | `u8` | 1 | `0x00887A1A` |
| 25 | `dwField_25` | `u32` | 4 | `0x00887A39` |
| 26 | `dwField_26` | `u32` | 4 | `0x00887A47` |
| 27 | `byField_27` | `u8` | 1 | `0x00887A75` |

**Minimum size**: 66 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] byField_05                     u8
  [   1] byField_06                     u8
  [   2] dwField_07                     u32
  [   6] dwField_08                     u32
  [  10] dwField_09                     u32
  [  14] dwField_10                     u32
  [  18] dwField_11                     u32
  [  22] dwField_12                     u32
  [  26] byField_13                     u8
  [  27] byField_14                     u8
  [  28] dwField_15                     u32
  [  32] byField_16                     u8
  [  33] dwField_17                     u32
  [  37] byField_18                     u8
  [  38] byField_19                     u8
  [  39] byField_20                     u8
  [  40] byField_21                     u8
  [  41] dwField_22                     u32
  [  45] dwField_23                     u32
  [  49] byField_24                     u8
  [  50] dwField_25                     u32
  [  54] dwField_26                     u32
  [  58] byField_27                     u8
```
