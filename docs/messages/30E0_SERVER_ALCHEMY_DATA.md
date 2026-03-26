# SERVER_ALCHEMY_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30E0` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008735D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u32` | 4 | `0x00873603` |
| 2 | `dwParam2` | `u32` | 4 | `0x00873611` |

**Total size**: 8 bytes


### String References
| String | Type |
|--------|------|
| `PARAM_CURE_ALL` | Debug |
| `STATUS_CURE_COS` | Debug |

### Structure Summary

```
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
```
