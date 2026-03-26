# CLIENT_JOB_DETAIL

| Property | Value |
|----------|-------|
| Opcode | `0xB107` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x008897C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088980A` |
| 2 | `byUnknown` | `bytes` | variable | `0x0088983E` |
| 3 | `bySlotType` | `u8` | 1 | `0x0088984C` |
| 4 | `dwItemID` | `u32` | 4 | `0x0088985A` |
| 5 | `dwParam1` | `u32` | 4 | `0x008898CD` |
| 6 | `byHasExtra` | `u8` | 1 | `0x008898DB` |
| 7 | `dwMinLevel` | `u32` | 4 | `0x008898F9` |
| 8 | `byUnknown2` | `bytes` | variable | `0x00889AA9` |
| 9 | `bySlotType2` | `u8` | 1 | `0x00889AB7` |
| 10 | `byAction` | `u8` | 1 | `0x00889AC5` |
| 11 | `byConfirm` | `u8` | 1 | `0x00889AD3` |
| 12 | `dwParam2` | `u32` | 4 | `0x00889B52` |
| 13 | `dwParam3` | `u32` | 4 | `0x00889B60` |

**Minimum size**: 26 bytes + variable fields

### Structure Summary

```
  [   0] byType                         u8
  [   1] byUnknown                      bytes  (variable length)
  [   0] bySlotType                     u8
  [   1] dwItemID                       u32
  [   5] dwParam1                       u32
  [   9] byHasExtra                     u8
  [  10] dwMinLevel                     u32
  [  14] byUnknown2                     bytes  (variable length)
  [   0] bySlotType2                    u8
  [   1] byAction                       u8
  [   2] byConfirm                      u8
  [   3] dwParam2                       u32
  [   7] dwParam3                       u32
```
