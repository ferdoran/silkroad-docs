# SERVER_UNION_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x751A` |
| Direction | Server → Client |
| Group | Guild Extended |
| Handler(s) | `0x0089A590` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A5A1` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A5D0` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089A620` |
| 4 | `byField_04` | `u8` | 1 | `0x0089A62E` |
| 5 | `byField_05` | `u8` | 1 | `0x0089A63C` |
| 6 | `wField_06` | `u16` | 2 | `0x0089A64A` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] byField_05                     u8
  [   8] wField_06                      u16
```
