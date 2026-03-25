# CLIENT_BATTLE_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0xB51A` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x0089F010` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0089F062` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089F070` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089F07E` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 14 bytes + variable fields

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] wField_04                      u16
  [  14] bytesData_4                    bytes  (variable length)
```
