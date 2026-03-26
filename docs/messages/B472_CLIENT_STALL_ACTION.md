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
| 1 | `byAction` | `u8` | 1 | `0x0089973E` |
| 2 | `wErrorCode` | `u16` | 2 | `0x00899759` |
| 3 | `dwParam` | `u32` | 4 | `0x0089978A` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wErrorCode                     u16
  [   3] dwParam                        u32
```
