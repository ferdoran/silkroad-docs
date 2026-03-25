# CLIENT_BERSERK_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0FF` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00892C50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00892C80` |
| 2 | `byField_02` | `u8` | 1 | `0x00892C9C` |
| 3 | `wField_03` | `u16` | 2 | `0x00892D41` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
```
