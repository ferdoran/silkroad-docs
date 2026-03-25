# CLIENT_ENTITY_DESPAWN_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB06C` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008801E0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008801EE` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088020A` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] bytesData_2                    bytes  (variable length)
```
