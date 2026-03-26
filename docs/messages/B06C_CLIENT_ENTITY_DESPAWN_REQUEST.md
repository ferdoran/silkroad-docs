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
| 2 | `dwTargetUID` | `u32` | 4 | `0x0088020A` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_MSG_PARTYMATCH_DELETE_COMPLETE` | UI |
| `UIIT_MSG_PARTYMATCH_DELETE_COMPLETE2` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwTargetUID                    u32
  [   5] bytesData_2                    bytes  (variable length)
```
