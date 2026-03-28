# SERVER_ENTITY_SPEED_UPDATE

> **Corrected name** (server RE): Was `SERVER_PET_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30D0` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A51E0` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Target entity |
| 2 | `SpeedWalking` | `f32` | 4 | Walking speed |
| 3 | `SpeedRunning` | `f32` | 4 | Running speed |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] SpeedWalking                   f32
  [   8] SpeedRunning                   f32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A51EE` |
| 2 | `wPetUID` | `u16` | 2 | `0x008A5203` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>
