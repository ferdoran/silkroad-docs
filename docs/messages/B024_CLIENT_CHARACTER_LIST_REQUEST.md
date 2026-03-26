# CLIENT_CHARACTER_LIST_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB024` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A5750`, `0x008A4F80` |

## Handler 1: `0x008A5750`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A5770` |
| 2 | `byAction` | `u8` | 1 | `0x008A564E` |
| 3 | `byField_03` | `u8` | 1 | `0x008A5662` |
| 4 | `byField_04` | `u8` | 1 | `0x008A5674` |
| 5 | `wField_05` | `u16` | 2 | `0x008A5682` |
| 6 | `byField_06` | `u8` | 1 | `0x008A5789` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] byField_03                     u8
  [   6] byField_04                     u8
  [   7] wField_05                      u16
  [   9] byField_06                     u8
```

## Handler 2: `0x008A4F80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A4F92` |
| 2 | `byAction` | `u16` | 2 | `0x008A4FA0` |
| 3 | `bytesData_2` | `bytes[14]` | 14 | `0x008A4FAE` |

**Total size**: 20 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u16
  [   6] bytesData_2                    bytes[14]
```
