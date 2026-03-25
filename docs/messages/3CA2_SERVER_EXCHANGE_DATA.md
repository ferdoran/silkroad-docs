# SERVER_EXCHANGE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x3CA2` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x00884CA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00884D14` |
| 2 | `byField_02` | `u8` | 1 | `0x00884D22` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `byField_05` | `u8` | 1 | `0x0060135B` |
| 6 | `dwField_06` | `u32` | 4 | `0x00601371` |
| 7 | `dwField_07` | `u32` | 4 | `0x0060138C` |
| 8 | `dwField_08` | `u32` | 4 | `0x006013A6` |
| 9 | `dwField_09` | `u32` | 4 | `0x006013C1` |

**Minimum size**: 24 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byField_02                     u8
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] byField_05                     u8
  [   1] dwField_06                     u32
  [   5] dwField_07                     u32
  [   9] dwField_08                     u32
  [  13] dwField_09                     u32
```
