# SERVER_FORTRESS_INFO

| Property | Value |
|----------|-------|
| Opcode | `0x34D5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0088E210` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x0088E21F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088E249` |
| 3 | `wField_03` | `u16` | 2 | `0x0088E257` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] wParam                         u16
  [   2] dwField_02                     u32
  [   6] wField_03                      u16
```
