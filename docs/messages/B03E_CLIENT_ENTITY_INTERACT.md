# CLIENT_ENTITY_INTERACT

| Property | Value |
|----------|-------|
| Opcode | `0xB03E` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A78B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A78BF` |
| 2 | `byFlags` | `u8` | 1 | `0x008A78CD` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byFlags                        u8
```
