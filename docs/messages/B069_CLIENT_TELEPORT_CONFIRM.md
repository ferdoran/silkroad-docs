# CLIENT_TELEPORT_CONFIRM

| Property | Value |
|----------|-------|
| Opcode | `0xB069` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00880120` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088012F` |
| 2 | `dwPartyID` | `u32` | 4 | `0x00880172` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwPartyID                      u32
```
