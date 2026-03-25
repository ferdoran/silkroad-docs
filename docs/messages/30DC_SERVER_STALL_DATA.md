# SERVER_STALL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30DC` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00884A30`, `0x00881570` |

## Handler 1: `0x00884A30`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wStallNameLen` | `u16` | 2 | `0x004F7A7D` |
| 2 | `bytesStallName` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 2 bytes + variable fields

### Structure Summary

```
  [   0] wStallNameLen                  u16
  [   2] bytesStallName                 bytes  (variable length)
```

## Handler 2: `0x00881570`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wStallNameLen` | `u8` | 1 | `0x00881584` |
| 2 | `bytesStallName` | `u8` | 1 | `0x008815A3` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] wStallNameLen                  u8
  [   1] bytesStallName                 u8
```
