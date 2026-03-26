# CLIENT_JOB_ALIAS_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB157` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00872810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00872820` |
| 2 | `byStage` | `u8` | 1 | `0x0087284F` |
| 3 | `byAction` | `u8` | 1 | `0x00872865` |
| 4 | `dwTargetUID` | `u32` | 4 | `0x00872873` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byStage                        u8
  [   2] byAction                       u8
  [   3] dwTargetUID                    u32
```
