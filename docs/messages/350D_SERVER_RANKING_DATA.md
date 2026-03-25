# SERVER_RANKING_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x350D` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089AA00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AA4A` |
| 2 | `byField_02` | `u8` | 1 | `0x0089AA71` |
| 3 | `dwField_03` | `u32` | 4 | `0x005E6EC2` |
| 4 | `byField_04` | `u8` | 1 | `0x005E6ED0` |
| 5 | `dwField_05` | `u32` | 4 | `0x008BE549` |
| 6 | `byField_06` | `u8` | 1 | `0x008BE5DD` |
| 7 | `ullField_07` | `u64` | 8 | `0x008BE5ED` |
| 8 | `dwField_08` | `u32` | 4 | `0x008BE5FB` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008BE642` |
| 10 | `ullField_10` | `u64` | 8 | `0x008BE652` |
| 11 | `dwField_11` | `u32` | 4 | `0x008BE662` |
| 12 | `wField_12` | `u16` | 2 | `0x008BE6C9` |
| 13 | `wField_13` | `u16` | 2 | `0x008BE75F` |
| 14 | `byField_14` | `u8` | 1 | `0x008BE830` |
| 15 | `dwField_15` | `u32` | 4 | `0x008BE849` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE8F9` |
| 17 | `byField_17` | `u8` | 1 | `0x008BE927` |
| 18 | `byField_18` | `u8` | 1 | `0x008BE97D` |
| 19 | `dwField_19` | `u32` | 4 | `0x008BE98B` |
| 20 | `dwField_20` | `u32` | 4 | `0x008BE999` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE9DA` |
| 22 | `byField_22` | `u8` | 1 | `0x008BE9E8` |
| 23 | `dwField_23` | `u32` | 4 | `0x008BEAAE` |
| 24 | `wField_24` | `u16` | 2 | `0x0089AB01` |

**Minimum size**: 70 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] dwField_05                     u32
  [  11] byField_06                     u8
  [  12] ullField_07                    u64
  [  20] dwField_08                     u32
  [  24] bytesData_8                    bytes  (variable length)
  [   0] ullField_10                    u64
  [   8] dwField_11                     u32
  [  12] wField_12                      u16
  [  14] wField_13                      u16
  [  16] byField_14                     u8
  [  17] dwField_15                     u32
  [  21] dwField_16                     u32
  [  25] byField_17                     u8
  [  26] byField_18                     u8
  [  27] dwField_19                     u32
  [  31] dwField_20                     u32
  [  35] dwField_21                     u32
  [  39] byField_22                     u8
  [  40] dwField_23                     u32
  [  44] wField_24                      u16
```
