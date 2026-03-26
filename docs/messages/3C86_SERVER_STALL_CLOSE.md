# SERVER_STALL_CLOSE

| Property | Value |
|----------|-------|
| Opcode | `0x3C86` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089BCC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x0089BD06` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089BD30` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089BD3E` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089BDAC` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089BDBA` |

**Minimum size**: 16 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_CTL_TC_SAVE_BUFF_TIME_OVER` | UI |

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] dwField_03                     u32
  [   8] dwField_04                     u32
  [  12] dwField_05                     u32
```
