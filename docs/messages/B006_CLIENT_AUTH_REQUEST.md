# CLIENT_AUTH_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB006` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0086DB40` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byLocale` | `u8` | 1 | `0x0086DB4F` |
| 2 | `byVersion` | `u8` | 1 | `0x0086DB65` |
| 3 | `byPlatform` | `u8` | 1 | `0x0086DB73` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byLocale                       u8
  [   1] byVersion                      u8
  [   2] byPlatform                     u8
```
