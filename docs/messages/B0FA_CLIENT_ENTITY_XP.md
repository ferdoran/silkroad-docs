# CLIENT_ENTITY_XP

| Property | Value |
|----------|-------|
| Opcode | `0xB0FA` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881AE0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881B05` |
| 2 | `dwMinLevel` | `u32` | 4 | `0x00881B1B` |

**Total size**: 5 bytes


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_GUILD_GP_SUBSCRIPION_RESULT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwMinLevel                     u32
```
