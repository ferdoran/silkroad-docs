# SERVER_BATTLE_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x3530` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089AD90`, `0x0089AFA0` |

## Handler 1: `0x0089AD90`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AD9E` |
| 2 | `byField_02` | `u8` | 1 | `0x0089ADDC` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089ADF9` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
```

## Handler 2: `0x0089AFA0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwRefObjID` | `u32` | 4 | `0x0089AFBC` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089AFCA` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwRefObjID                     u32
  [   4] dwField_02                     u32
```
