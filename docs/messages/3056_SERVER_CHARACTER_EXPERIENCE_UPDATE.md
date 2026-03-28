# SERVER_CHARACTER_EXPERIENCE_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_UPDATE_MOVEMENT` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3056` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7020` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `SourceUniqueID` | `u32` | 4 | Entity that gave the experience |
| 2 | `ExpReceived` | `i64` | 8 | Experience gained (can be negative on death penalty) |
| 3 | `SPExpReceived` | `i64` | 8 | Skill point experience gained |

**Total size**: 20 bytes (+ optional trailing byte sometimes present)

### Structure Summary

```
  [   0] SourceUniqueID                 u32
  [   4] ExpReceived                    i64
  [  12] SPExpReceived                  i64
```
