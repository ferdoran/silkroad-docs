# SERVER_JOB_ALIAS

| Property | Value |
|----------|-------|
| Opcode | `0x3156` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00872810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00872820` |
| 2 | `byField_02` | `u8` | 1 | `0x0087284F` |
| 3 | `byField_03` | `u8` | 1 | `0x00872865` |
| 4 | `dwField_04` | `u32` | 4 | `0x00872873` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] dwField_04                     u32
```
