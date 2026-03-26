# CLIENT_ENTITY_DESELECT

| Property | Value |
|----------|-------|
| Opcode | `0xB03F` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880A20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00880A2E` |
| 2 | `wParam` | `u16` | 2 | `0x00880A43` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```
