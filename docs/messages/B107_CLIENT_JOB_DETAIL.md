# CLIENT_JOB_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB107` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x008897C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088980A` |
| 2 | `bytesData_1` | `bytes` | variable | `0x0088983E` |
| 3 | `byField_03` | `u8` | 1 | `0x0088984C` |
| 4 | `dwField_04` | `u32` | 4 | `0x0088985A` |
| 5 | `dwField_05` | `u32` | 4 | `0x008898CD` |
| 6 | `byField_06` | `u8` | 1 | `0x008898DB` |
| 7 | `dwField_07` | `u32` | 4 | `0x008898F9` |
| 8 | `bytesData_7` | `bytes` | variable | `0x00889AA9` |
| 9 | `byField_09` | `u8` | 1 | `0x00889AB7` |
| 10 | `byField_10` | `u8` | 1 | `0x00889AC5` |
| 11 | `byField_11` | `u8` | 1 | `0x00889AD3` |
| 12 | `dwField_12` | `u32` | 4 | `0x00889B52` |
| 13 | `dwField_13` | `u32` | 4 | `0x00889B60` |

**Minimum size**: 26 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
  [   0] byField_03                     u8
  [   1] dwField_04                     u32
  [   5] dwField_05                     u32
  [   9] byField_06                     u8
  [  10] dwField_07                     u32
  [  14] bytesData_7                    bytes  (variable length)
  [   0] byField_09                     u8
  [   1] byField_10                     u8
  [   2] byField_11                     u8
  [   3] dwField_12                     u32
  [   7] dwField_13                     u32
```
