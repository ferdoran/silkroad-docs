# CLIENT_COS_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB110` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00885920` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x004F7A7D` |
| 2 | `bytesData_1` | `bytes` | variable | `0x004F7AB9` |
| 3 | `byField_03` | `u8` | 1 | `0x008859A6` |
| 4 | `dwField_04` | `u32` | 4 | `0x008859B4` |
| 5 | `byField_05` | `u8` | 1 | `0x008859C2` |
| 6 | `dwField_06` | `u32` | 4 | `0x008859D0` |

**Minimum size**: 12 bytes + variable fields

### Structure Summary

```
  [   0] wParam                         u16
  [   2] bytesData_1                    bytes  (variable length)
  [   0] byField_03                     u8
  [   1] dwField_04                     u32
  [   5] byField_05                     u8
  [   6] dwField_06                     u32
```
