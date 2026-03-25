# SERVER_ENTITY_MOVEMENT

| Property | Value |
|----------|-------|
| Opcode | `0x3052` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A70D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byMovementType` | `u8` | 1 | `0x008A70F7` |
| 2 | `ullTargetUID` | `u64` | 8 | `0x008A7124` |
| 3 | `byState` | `u8` | 1 | `0x008A7132` |
| 4 | `dwSpeed` | `u32` | 4 | `0x008A71E6` |
| 5 | `byDirection` | `u8` | 1 | `0x008A71F4` |
| 6 | `wRegionID` | `u16` | 2 | `0x008A72CF` |
| 7 | `byAngle` | `u8` | 1 | `0x008A72F3` |
| 8 | `dwPosX` | `u32` | 4 | `0x008A7301` |
| 9 | `dwPosZ` | `u32` | 4 | `0x008A7455` |

**Total size**: 26 bytes

### Structure Summary

```
  [   0] byMovementType                 u8
  [   1] ullTargetUID                   u64
  [   9] byState                        u8
  [  10] dwSpeed                        u32
  [  14] byDirection                    u8
  [  15] wRegionID                      u16
  [  17] byAngle                        u8
  [  18] dwPosX                         u32
  [  22] dwPosZ                         u32
```
