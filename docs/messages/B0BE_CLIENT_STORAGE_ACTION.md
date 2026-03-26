# CLIENT_STORAGE_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB0BE` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A4A30`, `0x008A4B00` |

## Handler 1: `0x008A4A30`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u32` | 4 | `0x008A4A41` |
| 2 | `dwParam2` | `u32` | 4 | `0x008A4A4F` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
```

## Handler 2: `0x008A4B00`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u8` | 1 | `0x008A4B11` |
| 2 | `dwParam2` | `u32` | 4 | `0x008A4B3A` |
| 3 | `byField_03` | `u8` | 1 | `0x008A4B48` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A4B56` |
| 5 | `byField_05` | `u8` | 1 | `0x008A4B64` |
| 6 | `bytesData_5` | `bytes[3]` | 3 | `0x008A4B9D` |

**Total size**: 14 bytes

### Structure Summary

```
  [   0] dwParam1                       u8
  [   1] dwParam2                       u32
  [   5] byField_03                     u8
  [   6] dwField_04                     u32
  [  10] byField_05                     u8
  [  11] bytesData_5                    bytes[3]
```
