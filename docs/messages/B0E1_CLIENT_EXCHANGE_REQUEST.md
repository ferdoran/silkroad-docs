# CLIENT_EXCHANGE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0E1` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00884DD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byJobType` | `u8` | 1 | `0x00884E1B` |
| 2 | `byAction` | `u8` | 1 | `0x00884E29` |
| 3 | `dwTargetUID` | `u32` | 4 | `0x00884E37` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byJobType                      u8
  [   1] byAction                       u8
  [   2] dwTargetUID                    u32
```
