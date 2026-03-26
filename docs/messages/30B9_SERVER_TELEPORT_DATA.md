# SERVER_TELEPORT_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30B9` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008720F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008720FF` |
| 2 | `wRegionID` | `u16` | 2 | `0x0087216F` |
| 3 | `dwPosX` | `u32` | 4 | `0x008721C1` |
| 4 | `wAngle` | `u16` | 2 | `0x008721CF` |

**Total size**: 9 bytes


### String References
| String | Type |
|--------|------|
| `IFStall` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wRegionID                      u16
  [   3] dwPosX                         u32
  [   7] wAngle                         u16
```
