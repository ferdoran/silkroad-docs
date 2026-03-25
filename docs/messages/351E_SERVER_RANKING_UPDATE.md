# SERVER_RANKING_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x351E` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089A760`, `0x0089A820` |

## Handler 1: `0x0089A760`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A76E` |
| 2 | `wField_02` | `u16` | 2 | `0x0089A783` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

## Handler 2: `0x0089A820`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A830` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A86D` |
| 3 | `byField_03` | `u8` | 1 | `0x0089A87B` |
| 4 | `dwField_04` | `u32` | 4 | `0x005F28DF` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x005F28FB` |
| 8 | `dwField_08` | `u32` | 4 | `0x005F2909` |
| 9 | `dwField_09` | `u32` | 4 | `0x005F2917` |
| 10 | `ullField_10` | `u64` | 8 | `0x005F2925` |
| 11 | `dwField_11` | `u32` | 4 | `0x005F2933` |

**Minimum size**: 30 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] dwField_04                     u32
  [   7] wField_05                      u16
  [   9] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] dwField_09                     u32
  [   9] ullField_10                    u64
  [  17] dwField_11                     u32
```
