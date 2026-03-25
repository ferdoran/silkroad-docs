# CLIENT_TELEPORT_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB067` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008800B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008800BF` |
| 2 | `wField_02` | `u16` | 2 | `0x008800F9` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
