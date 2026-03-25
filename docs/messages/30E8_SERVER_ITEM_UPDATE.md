# SERVER_ITEM_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x30E8` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880840`, `0x008806B0` |

## Handler 1: `0x00880840`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wItemDataLen` | `u16` | 2 | `0x0088084B` |
| 2 | `bytesItemData` | `bytes` | variable | `0x00841948` |

**Minimum size**: 2 bytes + variable fields

### Structure Summary

```
  [   0] wItemDataLen                   u16
  [   2] bytesItemData                  bytes  (variable length)
```

## Handler 2: `0x008806B0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wItemDataLen` | `u32` | 4 | `0x008806FB` |
| 2 | `bytesItemData` | `u8` | 1 | `0x00880709` |
| 3 | `byField_03` | `u8` | 1 | `0x00880785` |
| 4 | `byField_04` | `u8` | 1 | `0x008807A9` |
| 5 | `dwField_05` | `u32` | 4 | `0x008BB144` |
| 6 | `wField_06` | `u16` | 2 | `0x008BB174` |
| 7 | `dwField_07` | `u32` | 4 | `0x008BB192` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BB1A0` |
| 9 | `wField_09` | `u16` | 2 | `0x008BB1C4` |
| 10 | `dwField_10` | `u32` | 4 | `0x008BB1DE` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE549` |
| 12 | `byField_12` | `u8` | 1 | `0x008BE5DD` |
| 13 | `ullField_13` | `u64` | 8 | `0x008BE5ED` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BE5FB` |
| 15 | `bytesData_14` | `bytes` | variable | `0x008BE642` |
| 16 | `ullField_16` | `u64` | 8 | `0x008BE652` |
| 17 | `dwField_17` | `u32` | 4 | `0x008BE662` |
| 18 | `byField_18` | `u8` | 1 | `0x008BCE4B` |
| 19 | `ullField_19` | `u64` | 8 | `0x008BCE9F` |
| 20 | `byField_20` | `u8` | 1 | `0x008BB08E` |
| 21 | `byField_21` | `u8` | 1 | `0x008BB09C` |
| 22 | `byField_22` | `u8` | 1 | `0x008BB0BA` |
| 23 | `ullField_23` | `u64` | 8 | `0x008BB0C8` |
| 24 | `wField_24` | `u16` | 2 | `0x008BE6C9` |
| 25 | `wField_25` | `u16` | 2 | `0x004F7A7D` |
| 26 | `bytesData_25` | `bytes` | variable | `0x004F7AB9` |
| 27 | `dwField_27` | `u32` | 4 | `0x004F74CA` |
| 28 | `wField_28` | `u16` | 2 | `0x008BE75F` |
| 29 | `byField_29` | `u8` | 1 | `0x004F746A` |
| 30 | `byField_30` | `u8` | 1 | `0x008BE830` |
| 31 | `dwField_31` | `u32` | 4 | `0x008BE849` |
| 32 | `dwField_32` | `u32` | 4 | `0x008BE8F9` |
| 33 | `byField_33` | `u8` | 1 | `0x008BE927` |
| 34 | `byField_34` | `u8` | 1 | `0x008BE97D` |
| 35 | `dwField_35` | `u32` | 4 | `0x008BE98B` |
| 36 | `dwField_36` | `u32` | 4 | `0x008BE999` |
| 37 | `dwField_37` | `u32` | 4 | `0x008BE9DA` |
| 38 | `byField_38` | `u8` | 1 | `0x008BE9E8` |
| 39 | `dwField_39` | `u32` | 4 | `0x008BEAAE` |

**Minimum size**: 115 bytes + variable fields

### Structure Summary

```
  [   0] wItemDataLen                   u32
  [   4] bytesItemData                  u8
  [   5] byField_03                     u8
  [   6] byField_04                     u8
  [   7] dwField_05                     u32
  [  11] wField_06                      u16
  [  13] dwField_07                     u32
  [  17] dwField_08                     u32
  [  21] wField_09                      u16
  [  23] dwField_10                     u32
  [  27] dwField_11                     u32
  [  31] byField_12                     u8
  [  32] ullField_13                    u64
  [  40] dwField_14                     u32
  [  44] bytesData_14                   bytes  (variable length)
  [   0] ullField_16                    u64
  [   8] dwField_17                     u32
  [  12] byField_18                     u8
  [  13] ullField_19                    u64
  [  21] byField_20                     u8
  [  22] byField_21                     u8
  [  23] byField_22                     u8
  [  24] ullField_23                    u64
  [  32] wField_24                      u16
  [  34] wField_25                      u16
  [  36] bytesData_25                   bytes  (variable length)
  [   0] dwField_27                     u32
  [   4] wField_28                      u16
  [   6] byField_29                     u8
  [   7] byField_30                     u8
  [   8] dwField_31                     u32
  [  12] dwField_32                     u32
  [  16] byField_33                     u8
  [  17] byField_34                     u8
  [  18] dwField_35                     u32
  [  22] dwField_36                     u32
  [  26] dwField_37                     u32
  [  30] byField_38                     u8
  [  31] dwField_39                     u32
```
