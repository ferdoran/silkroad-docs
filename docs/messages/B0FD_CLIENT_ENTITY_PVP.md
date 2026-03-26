# CLIENT_ENTITY_PVP

| Property | Value |
|----------|-------|
| Opcode | `0xB0FD` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881E20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881E2E` |
| 2 | `wParam` | `u16` | 2 | `0x00881E48` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```
