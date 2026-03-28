# SERVER_CHARACTER_DATA_END

> **Corrected name** (server RE): Was `SERVER_EVENT_ITEM` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x34A6` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x008A8C00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A8C7F` |
| 2 | `byField_02` | `u8` | 1 | `0x008A8C99` |
| 3 | `byField_03` | `u8` | 1 | `0x008A8CB9` |
| 4 | `dwField_04` | `u32` | 4 | `0x008BB144` |
| 5 | `wField_05` | `u16` | 2 | `0x008BB174` |
| 6 | `dwField_06` | `u32` | 4 | `0x008BB192` |
| 7 | `dwField_07` | `u32` | 4 | `0x008BB1A0` |
| 8 | `wField_08` | `u16` | 2 | `0x008BB1C4` |
| 9 | `dwField_09` | `u32` | 4 | `0x008BB1DE` |
| 10 | `dwField_10` | `u32` | 4 | `0x008BE549` |
| 11 | `byField_11` | `u8` | 1 | `0x008BE5DD` |
| 12 | `ullField_12` | `u64` | 8 | `0x008BE5ED` |
| 13 | `dwField_13` | `u32` | 4 | `0x008BE5FB` |
| 14 | `bytesData_13` | `bytes` | variable | `0x008BE642` |
| 15 | `ullField_15` | `u64` | 8 | `0x008BE652` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE662` |
| 17 | `byField_17` | `u8` | 1 | `0x008BCE4B` |
| 18 | `ullField_18` | `u64` | 8 | `0x008BCE9F` |
| 19 | `byField_19` | `u8` | 1 | `0x008BB08E` |
| 20 | `byField_20` | `u8` | 1 | `0x008BB09C` |
| 21 | `byField_21` | `u8` | 1 | `0x008BB0BA` |
| 22 | `ullField_22` | `u64` | 8 | `0x008BB0C8` |
| 23 | `wField_23` | `u16` | 2 | `0x008BE6C9` |
| 24 | `wField_24` | `u16` | 2 | `0x004F7A7D` |
| 25 | `bytesData_24` | `bytes` | variable | `0x004F7AB9` |
| 26 | `dwField_26` | `u32` | 4 | `0x004F74CA` |
| 27 | `wField_27` | `u16` | 2 | `0x008BE75F` |
| 28 | `byField_28` | `u8` | 1 | `0x004F746A` |
| 29 | `byField_29` | `u8` | 1 | `0x008BE830` |
| 30 | `dwField_30` | `u32` | 4 | `0x008BE849` |
| 31 | `dwField_31` | `u32` | 4 | `0x008BE8F9` |
| 32 | `byField_32` | `u8` | 1 | `0x008BE927` |
| 33 | `byField_33` | `u8` | 1 | `0x008BE97D` |
| 34 | `dwField_34` | `u32` | 4 | `0x008BE98B` |
| 35 | `dwField_35` | `u32` | 4 | `0x008BE999` |
| 36 | `dwField_36` | `u32` | 4 | `0x008BE9DA` |
| 37 | `byField_37` | `u8` | 1 | `0x008BE9E8` |
| 38 | `dwField_38` | `u32` | 4 | `0x008BEAAE` |
| 39 | `bytesData_38` | `bytes` | variable | `0x008416B1` |
| 40 | `bytesData_39` | `bytes` | variable | `0x00841948` |

**Minimum size**: 111 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] dwField_04                     u32
  [   7] wField_05                      u16
  [   9] dwField_06                     u32
  [  13] dwField_07                     u32
  [  17] wField_08                      u16
  [  19] dwField_09                     u32
  [  23] dwField_10                     u32
  [  27] byField_11                     u8
  [  28] ullField_12                    u64
  [  36] dwField_13                     u32
  [  40] bytesData_13                   bytes  (variable length)
  [   0] ullField_15                    u64
  [   8] dwField_16                     u32
  [  12] byField_17                     u8
  [  13] ullField_18                    u64
  [  21] byField_19                     u8
  [  22] byField_20                     u8
  [  23] byField_21                     u8
  [  24] ullField_22                    u64
  [  32] wField_23                      u16
  [  34] wField_24                      u16
  [  36] bytesData_24                   bytes  (variable length)
  [   0] dwField_26                     u32
  [   4] wField_27                      u16
  [   6] byField_28                     u8
  [   7] byField_29                     u8
  [   8] dwField_30                     u32
  [  12] dwField_31                     u32
  [  16] byField_32                     u8
  [  17] byField_33                     u8
  [  18] dwField_34                     u32
  [  22] dwField_35                     u32
  [  26] dwField_36                     u32
  [  30] byField_37                     u8
  [  31] dwField_38                     u32
  [  35] bytesData_38                   bytes  (variable length)
  [   0] bytesData_39                   bytes  (variable length)
```
