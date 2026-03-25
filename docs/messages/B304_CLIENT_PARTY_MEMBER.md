# CLIENT_PARTY_MEMBER

| Property | Value |
|----------|-------|
| Opcode | `0xB304` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x00885E50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885E8D` |
| 2 | `wField_02` | `u16` | 2 | `0x00885EB1` |
| 3 | `byField_03` | `u8` | 1 | `0x00885ECD` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
  [   3] byField_03                     u8
  [   4] wField_04                      u16
  [   6] bytesData_4                    bytes  (variable length)
```
