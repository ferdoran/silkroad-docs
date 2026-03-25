# SERVER_TELEPORT_START

| Property | Value |
|----------|-------|
| Opcode | `0x30B7` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008721B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTeleportID` | `u32` | 4 | `0x008721C1` |
| 2 | `wDestRegion` | `u16` | 2 | `0x008721CF` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] dwTeleportID                   u32
  [   4] wDestRegion                    u16
```
