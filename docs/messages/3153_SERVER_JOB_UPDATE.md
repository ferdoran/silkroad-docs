# SERVER_JOB_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x3153` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x008825D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x008825F5` |
| 2 | `byField_02` | `u8` | 1 | `0x00882603` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] byField_02                     u8
```
