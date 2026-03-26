# CLIENT_ENTITY_EQUIPMENT

| Property | Value |
|----------|-------|
| Opcode | `0xB0E5` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088A130` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088A16F` |
| 2 | `byJobRankType` | `u8` | 1 | `0x0088A189` |
| 3 | `byJobLevel` | `u8` | 1 | `0x0088A197` |
| 4 | `byHasData` | `u8` | 1 | `0x0088A1A5` |
| 5 | `byCount1` | `u8` | 1 | `0x0088A210` |
| 6 | `bySlot1` | `u16` | 2 | `0x0087356D` |
| 7 | `dwRefItemID1` | `bytes` | variable | `0x008735A9` |
| 8 | `byOptLevel1` | `u8` | 1 | `0x0088A22C` |
| 9 | `byCount2` | `u32` | 4 | `0x0088A23A` |
| 10 | `bySlot2` | `u8` | 1 | `0x0088A248` |
| 11 | `dwRefItemID2` | `u8` | 1 | `0x0088A316` |
| 12 | `byOptLevel2` | `u8` | 1 | `0x0088A332` |
| 13 | `wExtraParam` | `u32` | 4 | `0x0088A340` |
| 14 | `byExtra1` | `u16` | 2 | `0x0088A3BA` |
| 15 | `byExtra2` | `u8` | 1 | `0x0088A3C8` |
| 16 | `byField_16` | `u8` | 1 | `0x0088A3D6` |

**Minimum size**: 23 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byJobRankType                  u8
  [   2] byJobLevel                     u8
  [   3] byHasData                      u8
  [   4] byCount1                       u8
  [   5] bySlot1                        u16
  [   7] dwRefItemID1                   bytes  (variable length)
  [   0] byOptLevel1                    u8
  [   1] byCount2                       u32
  [   5] bySlot2                        u8
  [   6] dwRefItemID2                   u8
  [   7] byOptLevel2                    u8
  [   8] wExtraParam                    u32
  [  12] byExtra1                       u16
  [  14] byExtra2                       u8
  [  15] byField_16                     u8
```
