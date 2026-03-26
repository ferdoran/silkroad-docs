# CLIENT_EXCHANGE_CONFIRM

| Property | Value |
|----------|-------|
| Opcode | `0xB0E2` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008890B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008890C1` |
| 2 | `byAction` | `u8` | 1 | `0x008890DE` |
| 3 | `byConfirm` | `u8` | 1 | `0x008890EC` |
| 4 | `dwParam` | `u32` | 4 | `0x008890FA` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byAction                       u8
  [   2] byConfirm                      u8
  [   3] dwParam                        u32
```
