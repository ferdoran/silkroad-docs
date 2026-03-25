# CLIENT_INVENTORY_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB081` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008847D0`, `0x0088AA60` |

## Handler 1: `0x008847D0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00884801` |
| 2 | `wSlot1` | `u16` | 2 | `0x0088481D` |
| 3 | `wSlot2` | `u16` | 2 | `0x00884919` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wSlot1                         u16
  [   3] wSlot2                         u16
```

## Handler 2: `0x0088AA60`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0088AAAF` |
| 2 | `wSlot1` | `u32` | 4 | `0x0088AABD` |
| 3 | `wSlot2` | `bytes` | variable | `0x00841948` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `byField_06` | `u8` | 1 | `0x0088AD93` |
| 7 | `byField_07` | `u8` | 1 | `0x008859A6` |
| 8 | `dwField_08` | `u32` | 4 | `0x008859B4` |
| 9 | `byField_09` | `u8` | 1 | `0x008859C2` |
| 10 | `dwField_10` | `u32` | 4 | `0x008859D0` |
| 11 | `dwField_11` | `u32` | 4 | `0x00889CCE` |
| 12 | `byField_12` | `u8` | 1 | `0x00889CDB` |
| 13 | `dwField_13` | `u32` | 4 | `0x00889CE8` |
| 14 | `byField_14` | `u8` | 1 | `0x00889CF5` |
| 15 | `byField_15` | `u8` | 1 | `0x00889D02` |
| 16 | `dwField_16` | `u32` | 4 | `0x00889D0F` |
| 17 | `dwField_17` | `u32` | 4 | `0x00889D1C` |
| 18 | `wField_18` | `u16` | 2 | `0x00889D2A` |
| 19 | `dwField_19` | `u32` | 4 | `0x00889D6F` |

**Minimum size**: 43 bytes + variable fields

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wSlot1                         u32
  [   5] wSlot2                         bytes  (variable length)
  [   0] wField_04                      u16
  [   2] bytesData_4                    bytes  (variable length)
  [   0] byField_06                     u8
  [   1] byField_07                     u8
  [   2] dwField_08                     u32
  [   6] byField_09                     u8
  [   7] dwField_10                     u32
  [  11] dwField_11                     u32
  [  15] byField_12                     u8
  [  16] dwField_13                     u32
  [  20] byField_14                     u8
  [  21] byField_15                     u8
  [  22] dwField_16                     u32
  [  26] dwField_17                     u32
  [  30] wField_18                      u16
  [  32] dwField_19                     u32
```
