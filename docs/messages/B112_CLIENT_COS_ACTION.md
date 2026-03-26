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
| 1 | `byAction1` | `u8` | 1 | `0x00881ECE` |
| 2 | `wParam1` | `u16` | 2 | `0x00881EE8` |
| 3 | `byAction2` | `u8` | 1 | `0x00881F3E` |
| 4 | `wParam2` | `u16` | 2 | `0x00881F58` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byAction1                      u8
  [   1] wParam1                        u16
  [   3] byAction2                      u8
  [   4] wParam2                        u16
```
