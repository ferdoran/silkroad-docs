# CLIENT_ENTITY_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB03C` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A7720` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A7731` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A774C` |
| 3 | `byParam1` | `u8` | 1 | `0x008A775A` |
| 4 | `dwParam2` | `u32` | 4 | `0x008A7768` |
| 5 | `wParam3` | `u16` | 2 | `0x008A77F4` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwTargetUID                    u32
  [   5] byParam1                       u8
  [   6] dwParam2                       u32
  [  10] wParam3                        u16
```
