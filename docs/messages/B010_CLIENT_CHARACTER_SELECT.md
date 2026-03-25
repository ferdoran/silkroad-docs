# CLIENT_CHARACTER_SELECT

| Property | Value |
|----------|-------|
| Opcode | `0xB010` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A7A20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7A2E` |
| 2 | `wField_02` | `u16` | 2 | `0x008A7A43` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
