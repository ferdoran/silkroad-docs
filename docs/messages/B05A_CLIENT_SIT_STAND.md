# CLIENT_SIT_STAND

| Property | Value |
|----------|-------|
| Opcode | `0xB05A` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883520` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088355C` |
| 2 | `wField_02` | `u16` | 2 | `0x008835FD` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
