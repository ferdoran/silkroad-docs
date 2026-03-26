# CLIENT_STALL_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB0D9` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00881450` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088145E` |
| 2 | `dwAction` | `u32` | 4 | `0x00881474` |
| 3 | `wParam` | `u16` | 2 | `0x0088149C` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwAction                       u32
  [   5] wParam                         u16
```
