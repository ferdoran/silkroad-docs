# CLIENT_GAME_OPTION

| Property | Value |
|----------|-------|
| Opcode | `0xB04B` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00888E30` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00888E41` |
| 2 | `byField_02` | `u8` | 1 | `0x00888E74` |
| 3 | `byField_03` | `u8` | 1 | `0x00888F44` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
```
