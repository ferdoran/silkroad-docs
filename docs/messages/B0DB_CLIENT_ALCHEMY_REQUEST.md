# CLIENT_ALCHEMY_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0DB` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D570` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0088D57F` |
| 2 | `byAction` | `u8` | 1 | `0x0088D58D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
```
