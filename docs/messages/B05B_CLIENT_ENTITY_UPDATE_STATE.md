# CLIENT_ENTITY_UPDATE_STATE

| Property | Value |
|----------|-------|
| Opcode | `0xB05B` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881690` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008816A1` |
| 2 | `ullField_02` | `u64` | 8 | `0x008816C3` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] ullField_02                    u64
```
