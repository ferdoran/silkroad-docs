# CLIENT_COS_INFO

| Property | Value |
|----------|-------|
| Opcode | `0xB116` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x008A7690`, `0x008A7B80` |

## Handler 1: `0x008A7690`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A76A1` |
| 2 | `byFlag1` | `u8` | 1 | `0x008A76AF` |
| 3 | `byFlag2` | `u8` | 1 | `0x008A76D5` |
| 4 | `byExtra` | `u8` | 1 | `0x008A76F9` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byFlag1                        u8
  [   5] byFlag2                        u8
  [   6] byExtra                        u8
```

## Handler 2: `0x008A7B80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u8` | 1 | `0x008A7B8E` |
| 2 | `byFlag1` | `u16` | 2 | `0x008A7BA8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u8
  [   1] byFlag1                        u16
```
