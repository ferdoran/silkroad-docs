# CLIENT_PARTY_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB0B3` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0087A260` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0087A2B3` |
| 2 | `dwStallID` | `u32` | 4 | `0x0087A2FD` |
| 3 | `dwParam1` | `u32` | 4 | `0x0087A32A` |
| 4 | `byExtra` | `u8` | 1 | `0x0087A387` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x00872337` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BE549` |
| 9 | `byField_09` | `u8` | 1 | `0x008BE5DD` |
| 10 | `ullField_10` | `u64` | 8 | `0x008BE5ED` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE5FB` |
| 12 | `bytesData_11` | `bytes` | variable | `0x008BE642` |
| 13 | `ullField_13` | `u64` | 8 | `0x008BE652` |
| 14 | `dwField_14` | `u32` | 4 | `0x008BE662` |
| 15 | `wField_15` | `u16` | 2 | `0x008BE6C9` |
| 16 | `wField_16` | `u16` | 2 | `0x008BE75F` |
| 17 | `byField_17` | `u8` | 1 | `0x008BE830` |
| 18 | `dwField_18` | `u32` | 4 | `0x008BE849` |
| 19 | `dwField_19` | `u32` | 4 | `0x008BE8F9` |
| 20 | `byField_20` | `u8` | 1 | `0x008BE927` |
| 21 | `byField_21` | `u8` | 1 | `0x008BE97D` |
| 22 | `dwField_22` | `u32` | 4 | `0x008BE98B` |
| 23 | `dwField_23` | `u32` | 4 | `0x008BE999` |
| 24 | `dwField_24` | `u32` | 4 | `0x008BE9DA` |
| 25 | `byField_25` | `u8` | 1 | `0x008BE9E8` |
| 26 | `dwField_26` | `u32` | 4 | `0x008BEAAE` |
| 27 | `byField_27` | `u8` | 1 | `0x00872370` |
| 28 | `wField_28` | `u16` | 2 | `0x00872389` |
| 29 | `ullField_29` | `u64` | 8 | `0x0087239A` |
| 30 | `byField_30` | `u8` | 1 | `0x008723FD` |
| 31 | `bytesData_30` | `bytes` | variable | `0x00841948` |

**Minimum size**: 86 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_WARENETWORK_BUY_SUCCESS` | UI |
| `UIIT_MSG_WARENETWORK_CHARGE` | UI |
| `UIIT_MSG_STREET_STORE_SELL_COMMODITY` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwStallID                      u32
  [   5] dwParam1                       u32
  [   9] byExtra                        u8
  [  10] wField_05                      u16
  [  12] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] byField_09                     u8
  [   6] ullField_10                    u64
  [  14] dwField_11                     u32
  [  18] bytesData_11                   bytes  (variable length)
  [   0] ullField_13                    u64
  [   8] dwField_14                     u32
  [  12] wField_15                      u16
  [  14] wField_16                      u16
  [  16] byField_17                     u8
  [  17] dwField_18                     u32
  [  21] dwField_19                     u32
  [  25] byField_20                     u8
  [  26] byField_21                     u8
  [  27] dwField_22                     u32
  [  31] dwField_23                     u32
  [  35] dwField_24                     u32
  [  39] byField_25                     u8
  [  40] dwField_26                     u32
  [  44] byField_27                     u8
  [  45] wField_28                      u16
  [  47] ullField_29                    u64
  [  55] byField_30                     u8
  [  56] bytesData_30                   bytes  (variable length)
```
