# CLIENT_ENTITY_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB0ED` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088A820`, `0x008867A0` |

## Handler 1: `0x0088A820`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUnknown` | `bytes` | variable | `0x0088A864` |
| 2 | `dwUniqueID` | `u32` | 4 | `0x0088A872` |
| 3 | `byAction` | `u8` | 1 | `0x0088A8BB` |
| 4 | `bySubAction` | `u8` | 1 | `0x0088A8C9` |
| 5 | `dwParam` | `u32` | 4 | `0x0088A8E0` |

**Minimum size**: 10 bytes + variable fields

### Structure Summary

```
  [   0] byUnknown                      bytes  (variable length)
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
  [   5] bySubAction                    u8
  [   6] dwParam                        u32
```

## Handler 2: `0x008867A0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byUnknown` | `u32` | 4 | `0x008867FC` |
| 2 | `dwUniqueID` | `u8` | 1 | `0x0088680A` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byUnknown                      u32
  [   4] dwUniqueID                     u8
```
