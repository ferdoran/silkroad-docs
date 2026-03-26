# CLIENT_ENTITY_GUILD

| Property | Value |
|----------|-------|
| Opcode | `0xB0FB` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881D80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881D8E` |
| 2 | `wParam` | `u16` | 2 | `0x00881DA8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```
