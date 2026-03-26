# CLIENT_ENTITY_DETAIL_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB071` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A5FD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A600B` |
| 2 | `wParam` | `u16` | 2 | `0x008A6020` |
| 3 | `byAction` | `bytes` | variable | `0x008A6052` |
| 4 | `dwUniqueID1` | `u32` | 4 | `0x008A6060` |
| 5 | `dwUniqueID2` | `u32` | 4 | `0x008A606E` |
| 6 | `dwTargetUID` | `u32` | 4 | `0x008A607C` |
| 7 | `dwField_07` | `u32` | 4 | `0x00A54C5D` |
| 8 | `byField_08` | `u8` | 1 | `0x00A54C7F` |
| 9 | `byField_09` | `u8` | 1 | `0x00A548F6` |
| 10 | `byField_10` | `u8` | 1 | `0x00A54904` |
| 11 | `dwField_11` | `u32` | 4 | `0x00A54CBB` |
| 12 | `wField_12` | `u16` | 2 | `0x00A54D1F` |
| 13 | `bytesData_12` | `bytes[12]` | 12 | `0x00A54D2D` |
| 14 | `bytesData_13` | `bytes` | variable | `0x00A54E02` |
| 15 | `bytesData_14` | `bytes[12]` | 12 | `0x00A54E10` |
| 16 | `bytesData_15` | `bytes` | variable | `0x008416B1` |
| 17 | `bytesData_16` | `bytes` | variable | `0x00841948` |

**Minimum size**: 52 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wParam                         u16
  [   3] byAction                       bytes  (variable length)
  [   0] dwUniqueID1                    u32
  [   4] dwUniqueID2                    u32
  [   8] dwTargetUID                    u32
  [  12] dwField_07                     u32
  [  16] byField_08                     u8
  [  17] byField_09                     u8
  [  18] byField_10                     u8
  [  19] dwField_11                     u32
  [  23] wField_12                      u16
  [  25] bytesData_12                   bytes[12]
  [  37] bytesData_13                   bytes  (variable length)
  [   0] bytesData_14                   bytes[12]
  [  12] bytesData_15                   bytes  (variable length)
  [   0] bytesData_16                   bytes  (variable length)
```
