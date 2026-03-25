# HANDSHAKE

| Property | Value |
|----------|-------|
| Opcode | `0x5000` |
| Direction | Bidirectional |
| Group | Security/Handshake |
| Handler(s) | `0x004B1DA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byFlag` | `u8` | 1 | `0x004B1E06` |
| 2 | `bytesSecurity` | `bytes` | variable | `0x004B1E1B` |
| 3 | `dwClientSeed` | `u32` | 4 | `0x004B1E33` |
| 4 | `dwServerSeed` | `u32` | 4 | `0x004B1E3A` |
| 5 | `ullChallenge` | `u64` | 8 | `0x004B1E50` |

**Minimum size**: 17 bytes + variable fields

### Structure Summary

```
  [   0] byFlag                         u8
  [   1] bytesSecurity                  bytes  (variable length)
  [   0] dwClientSeed                   u32
  [   4] dwServerSeed                   u32
  [   8] ullChallenge                   u64
```
