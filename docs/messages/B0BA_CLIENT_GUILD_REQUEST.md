# CLIENT_GUILD_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0BA` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872500`, `0x00873D60` |

## Handler 1: `0x00872500`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087250E` |
| 2 | `byConfirm` | `u8` | 1 | `0x00872532` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byConfirm                      u8
```

## Handler 2: `0x00873D60`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u32` | 4 | `0x00873DCA` |
| 2 | `byConfirm` | `u16` | 2 | `0x004F7A7D` |
| 3 | `dwUniqueID` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u32
  [   4] byConfirm                      u16
  [   6] dwUniqueID                     bytes  (variable length)
```
