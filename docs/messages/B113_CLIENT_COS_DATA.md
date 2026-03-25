# CLIENT_COS_DATA

| Property | Value |
|----------|-------|
| Opcode | `0xB113` |
| Direction | Client → Server |
| Group | Client Extended |
| Handler(s) | `0x00885AE0`, `0x00881F80` |

## Handler 1: `0x00885AE0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885B0F` |
| 2 | `dwField_02` | `u32` | 4 | `0x00885B25` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
```

## Handler 2: `0x00881F80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881F8E` |
| 2 | `wField_02` | `u16` | 2 | `0x00881FA8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```
