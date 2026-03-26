# CLIENT_ENTITY_SP

| Property | Value |
|----------|-------|
| Opcode | `0xB0F6` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881A70` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881A7E` |
| 2 | `wParam` | `u16` | 2 | `0x00881AB7` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```
