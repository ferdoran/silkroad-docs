# SYSTEM_KEEPALIVE

| Property | Value |
|----------|-------|
| Opcode | `0x0FFC` |
| Direction | System |
| Group | System/Debug |
| Handler(s) | `0x008A5230` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTimestamp` | `u32` | 4 | `0x008A523F` |
| 2 | `byFlag` | `u8` | 1 | `0x008A524D` |
| 3 | `dwSequence` | `u32` | 4 | `0x008A5291` |
| 4 | `dwLatency` | `u32` | 4 | `0x008A529F` |
| 5 | `dwChecksum` | `u32` | 4 | `0x008A52AD` |

**Total size**: 17 bytes

### Structure Summary

```
  [   0] dwTimestamp                    u32
  [   4] byFlag                         u8
  [   5] dwSequence                     u32
  [   9] dwLatency                      u32
  [  13] dwChecksum                     u32
```
