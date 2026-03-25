# SERVER_REGION_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x3908` |
| Direction | Server → Client |
| Group | Game Extended 9 |
| Handler(s) | `0x00881D00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881D0E` |
| 2 | `bytesData_1` | `bytes` | variable | `0x0099D945` |
| 3 | `dwField_03` | `u32` | 4 | `0x0099D953` |
| 4 | `byField_04` | `u8` | 1 | `0x0099D961` |
| 5 | `dwField_05` | `u32` | 4 | `0x0099DA06` |
| 6 | `byField_06` | `u8` | 1 | `0x0099DA14` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
  [   0] dwField_03                     u32
  [   4] byField_04                     u8
  [   5] dwField_05                     u32
  [   9] byField_06                     u8
```
