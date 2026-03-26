# CLIENT_ENTITY_INFO_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB074` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008809D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008809DE` |
| 2 | `wParam` | `u16` | 2 | `0x008809F8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```
