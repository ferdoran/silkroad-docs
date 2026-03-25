# CLIENT_QUEST_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB0CB` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A80A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A80B1` |
| 2 | `byField_02` | `u8` | 1 | `0x008A80BF` |
| 3 | `byField_03` | `u8` | 1 | `0x008A80CD` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byField_02                     u8
  [   5] byField_03                     u8
```
