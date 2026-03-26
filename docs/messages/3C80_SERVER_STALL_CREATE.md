# SERVER_STALL_CREATE

| Property | Value |
|----------|-------|
| Opcode | `0x3C80` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089C620`, `0x008A2110` |

## Handler 1: `0x0089C620`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089C66B` |
| 2 | `byField_02` | `u8` | 1 | `0x0089C6EB` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089C70A` |
| 4 | `byField_04` | `u8` | 1 | `0x0089C718` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x0089C737` |
| 8 | `byField_08` | `u8` | 1 | `0x0089C745` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089C753` |
| 10 | `wField_10` | `u16` | 2 | `0x0089C8E8` |

**Minimum size**: 17 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_DISSOLUTION_SUCCESS` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_ANNOUNCE` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_OTHER_USER` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT_ANNOUNCE` | UI |
| `UIIT_MSG_TC_MACHING_JOINING_MEMBER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] wField_05                      u16
  [   9] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] byField_08                     u8
  [   2] dwField_09                     u32
  [   6] wField_10                      u16
```

## Handler 2: `0x008A2110`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A215C` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A21F5` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A2203` |
| 4 | `dwField_04` | `u32` | 4 | `0x008A2211` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x008A222E` |
| 8 | `byField_08` | `u8` | 1 | `0x008A223C` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008A224E` |
| 10 | `byField_10` | `u8` | 1 | `0x008A225C` |
| 11 | `byField_11` | `u8` | 1 | `0x008A226A` |
| 12 | `dwField_12` | `u32` | 4 | `0x008A2278` |
| 13 | `byField_13` | `u8` | 1 | `0x008A2286` |
| 14 | `dwField_14` | `u32` | 4 | `0x008A2294` |
| 15 | `wField_15` | `u16` | 2 | `0x008A22A2` |
| 16 | `wField_16` | `u16` | 2 | `0x008A22B0` |
| 17 | `wField_17` | `u16` | 2 | `0x008A22BE` |
| 18 | `wField_18` | `u16` | 2 | `0x008A22CC` |
| 19 | `dwField_19` | `u32` | 4 | `0x008A25BE` |
| 20 | `byField_20` | `u8` | 1 | `0x008A25CC` |

**Minimum size**: 41 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_DISSOLUTION_SUCCESS` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_ANNOUNCE` | UI |
| `UIIT_STT_TC_OUT_TRAININGCAMP_OTHER_USER` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT` | UI |
| `UIIT_MSG_TC_EXPULSION_RESULT_ANNOUNCE` | UI |
| `UIIT_MSG_TC_MACHING_JOINING_MEMBER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] dwField_04                     u32
  [  13] wField_05                      u16
  [  15] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] byField_08                     u8
  [   2] bytesData_8                    bytes  (variable length)
  [   0] byField_10                     u8
  [   1] byField_11                     u8
  [   2] dwField_12                     u32
  [   6] byField_13                     u8
  [   7] dwField_14                     u32
  [  11] wField_15                      u16
  [  13] wField_16                      u16
  [  15] wField_17                      u16
  [  17] wField_18                      u16
  [  19] dwField_19                     u32
  [  23] byField_20                     u8
```
