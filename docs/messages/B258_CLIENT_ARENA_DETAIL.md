# CLIENT_ARENA_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB258` |
| Direction | Client → Server |
| Group | Client Extended 2 |
| Handler(s) | `0x00895810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00895897` |
| 2 | `dwField_02` | `u32` | 4 | `0x008958B1` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwField_05` | `u32` | 4 | `0x008958CE` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
```
