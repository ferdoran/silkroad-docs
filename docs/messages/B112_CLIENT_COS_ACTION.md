# CLIENT_COS_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB112` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00881EC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881ECE` |
| 2 | `wField_02` | `u16` | 2 | `0x00881EE8` |
| 3 | `byField_03` | `u8` | 1 | `0x00881F3E` |
| 4 | `wField_04` | `u16` | 2 | `0x00881F58` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] byField_03                     u8
  [   4] wField_04                      u16
```
