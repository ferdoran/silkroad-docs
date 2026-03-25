# CLIENT_RANKING_ENTRY

| Property | Value |
|----------|-------|
| Opcode | `0xB50A` |
| Direction | Client → Server |
| Group | Client Extended 5 |
| Handler(s) | `0x0089AB50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AB5E` |
| 2 | `byField_02` | `u8` | 1 | `0x0089AB9E` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwField_05` | `u32` | 4 | `0x005ED4D5` |
| 6 | `dwField_06` | `u32` | 4 | `0x008BE549` |
| 7 | `byField_07` | `u8` | 1 | `0x008BE5DD` |
| 8 | `ullField_08` | `u64` | 8 | `0x008BE5ED` |
| 9 | `dwField_09` | `u32` | 4 | `0x008BE5FB` |
| 10 | `bytesData_9` | `bytes` | variable | `0x008BE642` |
| 11 | `ullField_11` | `u64` | 8 | `0x008BE652` |
| 12 | `dwField_12` | `u32` | 4 | `0x008BE662` |
| 13 | `wField_13` | `u16` | 2 | `0x008BE6C9` |
| 14 | `wField_14` | `u16` | 2 | `0x008BE75F` |
| 15 | `byField_15` | `u8` | 1 | `0x008BE830` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE849` |
| 17 | `dwField_17` | `u32` | 4 | `0x008BE8F9` |
| 18 | `byField_18` | `u8` | 1 | `0x008BE927` |
| 19 | `byField_19` | `u8` | 1 | `0x008BE97D` |
| 20 | `dwField_20` | `u32` | 4 | `0x008BE98B` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE999` |
| 22 | `dwField_22` | `u32` | 4 | `0x008BE9DA` |
| 23 | `byField_23` | `u8` | 1 | `0x008BE9E8` |
| 24 | `dwField_24` | `u32` | 4 | `0x008BEAAE` |

**Minimum size**: 69 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] dwField_06                     u32
  [   8] byField_07                     u8
  [   9] ullField_08                    u64
  [  17] dwField_09                     u32
  [  21] bytesData_9                    bytes  (variable length)
  [   0] ullField_11                    u64
  [   8] dwField_12                     u32
  [  12] wField_13                      u16
  [  14] wField_14                      u16
  [  16] byField_15                     u8
  [  17] dwField_16                     u32
  [  21] dwField_17                     u32
  [  25] byField_18                     u8
  [  26] byField_19                     u8
  [  27] dwField_20                     u32
  [  31] dwField_21                     u32
  [  35] dwField_22                     u32
  [  39] byField_23                     u8
  [  40] dwField_24                     u32
```
