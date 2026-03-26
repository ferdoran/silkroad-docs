# SERVER_PET_STATUS

| Property | Value |
|----------|-------|
| Opcode | `0x30D3` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00881100`, `0x00881170` |

## Handler 1: `0x00881100`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byStatus` | `u8` | 1 | `0x0088110C` |

**Total size**: 1 bytes


### String References
| String | Type |
|--------|------|
| `(Test_GM)PKCnt D:%d` | Debug |


### String References
| String | Type |
|--------|------|
| `(Test_GM)PKLevel L:%d` | Debug |

### Structure Summary

```
  [   0] byStatus                       u8
```

## Handler 2: `0x00881170`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byStatus` | `u16` | 2 | `0x0088117C` |

**Total size**: 2 bytes


### String References
| String | Type |
|--------|------|
| `(Test_GM)PKCnt D:%d` | Debug |


### String References
| String | Type |
|--------|------|
| `(Test_GM)PKLevel L:%d` | Debug |

### Structure Summary

```
  [   0] byStatus                       u16
```
