# CLIENT_PARTY_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB0B5` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873FF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087403B` |
| 2 | `dwStallID` | `bytes` | variable | `0x00841948` |
| 3 | `bySlotType` | `u32` | 4 | `0x008740DD` |
| 4 | `byItemType` | `u16` | 2 | `0x004F7A7D` |
| 5 | `byDurability` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byQuantity` | `u8` | 1 | `0x008740F9` |
| 7 | `wRefItemID` | `u8` | 1 | `0x00874107` |
| 8 | `ullSerialNum` | `u8` | 1 | `0x008741DE` |
| 9 | `byOptLevel` | `u32` | 4 | `0x008BB144` |
| 10 | `byExtra` | `u16` | 2 | `0x008BB174` |
| 11 | `dwPrice` | `u32` | 4 | `0x008BB192` |
| 12 | `wStackCount` | `u32` | 4 | `0x008BB1A0` |
| 13 | `wField_13` | `u16` | 2 | `0x008BB1C4` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BB1DE` |
| 15 | `dwField_15` | `u32` | 4 | `0x008BE549` |
| 16 | `byField_16` | `u8` | 1 | `0x008BE5DD` |
| 17 | `ullField_17` | `u64` | 8 | `0x008BE5ED` |
| 18 | `dwField_18` | `u32` | 4 | `0x008BE5FB` |
| 19 | `bytesData_18` | `bytes` | variable | `0x008BE642` |
| 20 | `ullField_20` | `u64` | 8 | `0x008BE652` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE662` |
| 22 | `byField_22` | `u8` | 1 | `0x008BCE4B` |
| 23 | `ullField_23` | `u64` | 8 | `0x008BCE9F` |
| 24 | `byField_24` | `u8` | 1 | `0x008BB08E` |
| 25 | `byField_25` | `u8` | 1 | `0x008BB09C` |
| 26 | `byField_26` | `u8` | 1 | `0x008BB0BA` |
| 27 | `ullField_27` | `u64` | 8 | `0x008BB0C8` |
| 28 | `wField_28` | `u16` | 2 | `0x008BE6C9` |
| 29 | `dwField_29` | `u32` | 4 | `0x004F74CA` |
| 30 | `wField_30` | `u16` | 2 | `0x008BE75F` |
| 31 | `byField_31` | `u8` | 1 | `0x004F746A` |
| 32 | `byField_32` | `u8` | 1 | `0x008BE830` |
| 33 | `dwField_33` | `u32` | 4 | `0x008BE849` |
| 34 | `dwField_34` | `u32` | 4 | `0x008BE8F9` |
| 35 | `byField_35` | `u8` | 1 | `0x008BE927` |
| 36 | `byField_36` | `u8` | 1 | `0x008BE97D` |
| 37 | `dwField_37` | `u32` | 4 | `0x008BE98B` |
| 38 | `dwField_38` | `u32` | 4 | `0x008BE999` |
| 39 | `dwField_39` | `u32` | 4 | `0x008BE9DA` |
| 40 | `byField_40` | `u8` | 1 | `0x008BE9E8` |
| 41 | `dwField_41` | `u32` | 4 | `0x008BEAAE` |
| 42 | `byField_42` | `u8` | 1 | `0x00874216` |
| 43 | `wField_43` | `u16` | 2 | `0x00874229` |
| 44 | `ullField_44` | `u64` | 8 | `0x0087423A` |
| 45 | `byField_45` | `u8` | 1 | `0x00874277` |
| 46 | `byField_46` | `u8` | 1 | `0x008742A3` |
| 47 | `dwField_47` | `u32` | 4 | `0x008742BA` |
| 48 | `wField_48` | `u16` | 2 | `0x00874349` |

**Minimum size**: 135 bytes + variable fields

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwStallID                      bytes  (variable length)
  [   0] bySlotType                     u32
  [   4] byItemType                     u16
  [   6] byDurability                   bytes  (variable length)
  [   0] byQuantity                     u8
  [   1] wRefItemID                     u8
  [   2] ullSerialNum                   u8
  [   3] byOptLevel                     u32
  [   7] byExtra                        u16
  [   9] dwPrice                        u32
  [  13] wStackCount                    u32
  [  17] wField_13                      u16
  [  19] dwField_14                     u32
  [  23] dwField_15                     u32
  [  27] byField_16                     u8
  [  28] ullField_17                    u64
  [  36] dwField_18                     u32
  [  40] bytesData_18                   bytes  (variable length)
  [   0] ullField_20                    u64
  [   8] dwField_21                     u32
  [  12] byField_22                     u8
  [  13] ullField_23                    u64
  [  21] byField_24                     u8
  [  22] byField_25                     u8
  [  23] byField_26                     u8
  [  24] ullField_27                    u64
  [  32] wField_28                      u16
  [  34] dwField_29                     u32
  [  38] wField_30                      u16
  [  40] byField_31                     u8
  [  41] byField_32                     u8
  [  42] dwField_33                     u32
  [  46] dwField_34                     u32
  [  50] byField_35                     u8
  [  51] byField_36                     u8
  [  52] dwField_37                     u32
  [  56] dwField_38                     u32
  [  60] dwField_39                     u32
  [  64] byField_40                     u8
  [  65] dwField_41                     u32
  [  69] byField_42                     u8
  [  70] wField_43                      u16
  [  72] ullField_44                    u64
  [  80] byField_45                     u8
  [  81] byField_46                     u8
  [  82] dwField_47                     u32
  [  86] wField_48                      u16
```
