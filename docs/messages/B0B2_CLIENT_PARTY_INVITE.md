# CLIENT_PARTY_INVITE

| Property | Value |
|----------|-------|
| Opcode | `0xB0B2` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873C10` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x00873C7D` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |
| 4 | `dwField_04` | `u32` | 4 | `0x00873C97` |

**Minimum size**: 10 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
  [   0] dwField_04                     u32
```
