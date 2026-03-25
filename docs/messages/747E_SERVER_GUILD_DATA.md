# SERVER_GUILD_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x747E` |
| Direction | Server → Client |
| Group | Guild/Union |
| Handler(s) | `0x00890AB0`, `0x00890FA0` |

## Handler 1: `0x00890AB0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00890AFB` |
| 2 | `byField_02` | `u8` | 1 | `0x00890B15` |
| 3 | `byField_03` | `u8` | 1 | `0x00890B23` |
| 4 | `byField_04` | `u8` | 1 | `0x00890B31` |
| 5 | `dwField_05` | `u32` | 4 | `0x00890C56` |
| 6 | `dwField_06` | `u32` | 4 | `0x00890C64` |
| 7 | `byField_07` | `u8` | 1 | `0x00890C72` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `dwField_10` | `u32` | 4 | `0x00890C8C` |
| 11 | `byField_11` | `u8` | 1 | `0x00890C9A` |
| 12 | `byField_12` | `u8` | 1 | `0x00890CA8` |
| 13 | `dwField_13` | `u32` | 4 | `0x00890CB6` |
| 14 | `wField_14` | `u16` | 2 | `0x004F7A7D` |
| 15 | `bytesData_14` | `bytes` | variable | `0x004F7AB9` |
| 16 | `dwField_16` | `u32` | 4 | `0x00890CD3` |
| 17 | `byField_17` | `u8` | 1 | `0x00890CE4` |
| 18 | `dwField_18` | `u32` | 4 | `0x00890CF5` |
| 19 | `dwField_19` | `u32` | 4 | `0x00890D06` |
| 20 | `wField_20` | `u16` | 2 | `0x00890F4D` |

**Minimum size**: 42 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] byField_07                     u8
  [  13] wField_08                      u16
  [  15] bytesData_8                    bytes  (variable length)
  [   0] dwField_10                     u32
  [   4] byField_11                     u8
  [   5] byField_12                     u8
  [   6] dwField_13                     u32
  [  10] wField_14                      u16
  [  12] bytesData_14                   bytes  (variable length)
  [   0] dwField_16                     u32
  [   4] byField_17                     u8
  [   5] dwField_18                     u32
  [   9] dwField_19                     u32
  [  13] wField_20                      u16
```

## Handler 2: `0x00890FA0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x00890FED` |
| 2 | `dwField_02` | `u32` | 4 | `0x00890FFB` |
| 3 | `dwField_03` | `u32` | 4 | `0x0088F4DD` |
| 4 | `dwField_04` | `u32` | 4 | `0x0088F4EA` |
| 5 | `byField_05` | `u8` | 1 | `0x0088F4F7` |
| 6 | `byField_06` | `u8` | 1 | `0x0088F504` |
| 7 | `dwField_07` | `u32` | 4 | `0x0088F511` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |

**Minimum size**: 24 bytes + variable fields

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] byField_05                     u8
  [  17] byField_06                     u8
  [  18] dwField_07                     u32
  [  22] wField_08                      u16
  [  24] bytesData_8                    bytes  (variable length)
```
