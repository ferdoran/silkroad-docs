# SERVER_FORTRESS_UPDATE

| Property | Value |
|----------|-------|
| Opcode | `0x34D2` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0089A250`, `0x0089A310` |

## Handler 1: `0x0089A250`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089A25E` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
```

## Handler 2: `0x0089A310`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A322` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A369` |
| 3 | `byField_03` | `u8` | 1 | `0x0089A377` |
| 4 | `byField_04` | `u8` | 1 | `0x0089A385` |
| 5 | `byField_05` | `u8` | 1 | `0x0089A393` |
| 6 | `byField_06` | `u8` | 1 | `0x0089A3A1` |
| 7 | `byField_07` | `u8` | 1 | `0x0089A3AF` |
| 8 | `byField_08` | `u8` | 1 | `0x0089A3BD` |
| 9 | `byField_09` | `u8` | 1 | `0x0089A3CB` |
| 10 | `byField_10` | `u8` | 1 | `0x0089A3D9` |
| 11 | `dwField_11` | `u32` | 4 | `0x0089A405` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089A413` |

**Total size**: 18 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] byField_05                     u8
  [   5] byField_06                     u8
  [   6] byField_07                     u8
  [   7] byField_08                     u8
  [   8] byField_09                     u8
  [   9] byField_10                     u8
  [  10] dwField_11                     u32
  [  14] dwField_12                     u32
```
