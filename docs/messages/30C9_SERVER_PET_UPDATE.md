# SERVER_PET_UPDATE

> **Corrected name** (server RE): Was `SERVER_EXCHANGE_CONFIRM` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30C9` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7A70` |

### Fields (Server RE)

Switched structure based on `UpdateType`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Pet/COS unique ID |
| 2 | `UpdateType` | `u8` | 1 | Type of update |

**UpdateType values:**

| UpdateType | Payload | Description |
|------------|---------|-------------|
| 1 | (none) | Pet unsummoned |
| 3 | `i64 ExpReceived, u32 SourceUniqueID` | Pet gained experience |
| 4 | `u16 HGP` | Hunger gauge updated |
| 7 | `u32 NewModelID` | Pet model changed (level up evolution) |

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] UpdateType                     u8
  switch UpdateType:
    case 1: (no data — unsummoned)
    case 3:
      [   5] ExpReceived                i64
      [  13] SourceUniqueID             u32
    case 4:
      [   5] HGP                        u16
    case 7:
      [   5] NewModelID                 u32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7A7E` |
| 2 | `wValue` | `u16` | 2 | `0x008A7A93` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>
