# CLIENT_ENTITY_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB03C` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A7720` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7731` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A774C` |
| 3 | `byField_03` | `u8` | 1 | `0x008A775A` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A7768` |
| 5 | `wField_05` | `u16` | 2 | `0x008A77F4` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] byField_03                     u8
  [   6] dwField_04                     u32
  [  10] wField_05                      u16
```
