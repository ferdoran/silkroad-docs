# CLIENT_CHARACTER_DELETE

| Property | Value |
|----------|-------|
| Opcode | `0xB025` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872740` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0087274F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0087275D` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
```
