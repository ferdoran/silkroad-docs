# CLIENT_ENTITY_SELECT

| Property | Value |
|----------|-------|
| Opcode | `0xB034` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880DB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00880DBE` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x00880DD9` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwTargetUID                    u32
```
