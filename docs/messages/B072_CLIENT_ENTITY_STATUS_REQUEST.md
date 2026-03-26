# CLIENT_ENTITY_STATUS_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB072` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A4B00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x008A4B11` |
| 2 | `dwParam1` | `u32` | 4 | `0x008A4B3A` |
| 3 | `bySubType` | `u8` | 1 | `0x008A4B48` |
| 4 | `dwUniqueID` | `u32` | 4 | `0x008A4B56` |
| 5 | `byFlags` | `u8` | 1 | `0x008A4B64` |
| 6 | `bytesPosition` | `bytes[3]` | 3 | `0x008A4B9D` |

**Total size**: 14 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] dwParam1                       u32
  [   5] bySubType                      u8
  [   6] dwUniqueID                     u32
  [  10] byFlags                        u8
  [  11] bytesPosition                  bytes[3]
```
