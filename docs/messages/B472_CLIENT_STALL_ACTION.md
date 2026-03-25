# CLIENT_STALL_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB472` |
| Direction | Client → Server |
| Group | Client Extended 4 |
| Handler(s) | `0x00899730` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089973E` |
| 2 | `wField_02` | `u16` | 2 | `0x00899759` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089978A` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] dwField_03                     u32
```
