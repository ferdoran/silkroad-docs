# CLIENT_INVENTORY_MOVE

| Property | Value |
|----------|-------|
| Opcode | `0xB082` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008803F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008803FB` |
| 2 | `byResult` | `u8` | 1 | `0x0088043E` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byResult                       u8
```
