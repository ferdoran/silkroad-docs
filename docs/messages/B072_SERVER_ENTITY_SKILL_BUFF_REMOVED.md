# SERVER_ENTITY_SKILL_BUFF_REMOVED

> **Corrected name** (server RE): Was `CLIENT_ENTITY_STATUS_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB072` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A4B00` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Success` | `bool` | 1 | Whether the buff was successfully removed |
| 2 | `BuffUniqueID` | `u32` | 4 | Unique instance ID of the removed buff (only if Success) |

**Minimum size**: 1 byte (failure), 5 bytes (success)

### Structure Summary

```
  [   0] Success                        bool
  if Success:
    [   1] BuffUniqueID                 u32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x008A4B11` |
| 2 | `dwParam1` | `u32` | 4 | `0x008A4B3A` |
| 3 | `bySubType` | `u8` | 1 | `0x008A4B48` |
| 4 | `dwUniqueID` | `u32` | 4 | `0x008A4B56` |
| 5 | `byFlags` | `u8` | 1 | `0x008A4B64` |
| 6 | `bytesPosition` | `bytes[3]` | 3 | `0x008A4B9D` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>
