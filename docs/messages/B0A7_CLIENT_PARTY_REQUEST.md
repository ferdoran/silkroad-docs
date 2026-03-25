# CLIENT_PARTY_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0A7` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873D60` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x00873DCA` |
| 2 | `wField_02` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wField_02                      u16
  [   6] bytesData_2                    bytes  (variable length)
```
