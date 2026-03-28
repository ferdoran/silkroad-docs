# SERVER_ENVIROMENT_CELESTIAL_POSITION

> **Corrected name** (server RE): Was `SERVER_CHARACTER_DATA` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3020` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008ABBA0` |
| Send site | `0x004E3EBA` (SR_GameServer.exe clean) |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `LocalTime` | `u32` | 4 | Server time value (DWORD) |
| 2 | `MoonPhase` | `u16` | 2 | Current moon phase index |
| 3 | `MoonAngle` | `u8` | 1 | Moon position angle |
| 4 | `SunAngle` | `u8` | 1 | Sun position angle |

### Structure Summary

```
  [0] LocalTime                          u32    // server time
  [4] MoonPhase                          u16    // moon phase index
  [6] MoonAngle                          u8     // moon position
  [7] SunAngle                           u8     // sun position
```

Total payload: **8 bytes**

### Binary Evidence

Disassembly of `fcn.004e3eb0` (VA `0x4E3EB0`), `eax` value before each `call 0x404090`:

| Write VA | `eax` (size) | Source |
|----------|-------------|--------|
| `0x004E3ED0` | 4 | `[this+8]` — time value |
| `0x004E3EF4` | 2 | `[celestial+0x20]` — moon phase |
| `0x004E3F04` | 1 | `[celestial+0x22]` — moon angle |
| `0x004E3F14` | 1 | `[celestial+0x23]` — sun angle |

> The same function continues to send `0x3057 SERVER_ENTITY_STATUS_UPDATE` (at `0x4E3F51`)
> and `0x304E SERVER_CHARACTER_INFO_UPDATE` (at `0x4E3FBF`).
