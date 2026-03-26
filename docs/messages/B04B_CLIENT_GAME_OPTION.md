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
| 2 | `byLockFlag` | `u8` | 1 | `0x00888E74` |
| 3 | `byConfirm` | `u8` | 1 | `0x00888F44` |

**Total size**: 3 bytes


### String References
| String | Type |
|--------|------|
| `Ghacha` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byLockFlag                     u8
  [   2] byConfirm                      u8
```
