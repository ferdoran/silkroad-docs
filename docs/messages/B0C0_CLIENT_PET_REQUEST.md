# CLIENT_PET_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0C0` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00886AC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00886AD1` |
| 2 | `wField_02` | `u16` | 2 | `0x00886AF6` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
