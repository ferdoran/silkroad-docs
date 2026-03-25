# CLIENT_GUILD_ACTION

| Property | Value |
|----------|-------|
| Opcode | `0xB30A` |
| Direction | Client → Server |
| Group | Client Extended 3 |
| Handler(s) | `0x008820B0`, `0x00886310` |

## Handler 1: `0x008820B0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008820BE` |
| 2 | `wField_02` | `u16` | 2 | `0x008820F5` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

## Handler 2: `0x00886310`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088635A` |
| 2 | `dwField_02` | `u32` | 4 | `0x008863A1` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwField_05` | `u32` | 4 | `0x008863BB` |
| 6 | `dwField_06` | `u32` | 4 | `0x0088645A` |
| 7 | `dwField_07` | `u32` | 4 | `0x00886499` |
| 8 | `byField_08` | `u8` | 1 | `0x008864A7` |
| 9 | `dwField_09` | `u32` | 4 | `0x00886667` |
| 10 | `dwField_10` | `u32` | 4 | `0x00886675` |
| 11 | `byField_11` | `u8` | 1 | `0x00886710` |

**Minimum size**: 29 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] dwField_06                     u32
  [   8] dwField_07                     u32
  [  12] byField_08                     u8
  [  13] dwField_09                     u32
  [  17] dwField_10                     u32
  [  21] byField_11                     u8
```
