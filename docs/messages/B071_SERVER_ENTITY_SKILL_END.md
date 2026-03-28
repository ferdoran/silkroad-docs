# SERVER_ENTITY_SKILL_END

> **Corrected name** (server RE): Was `CLIENT_ENTITY_DETAIL_REQUEST` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB071` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A5FD0` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Success` | `bool` | 1 | Whether the skill ended successfully |

If `Success`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `SkillUniqueID` | `u32` | 4 | Unique instance ID of the ending skill |
| 3 | `TargetUniqueID` | `u32` | 4 | Target entity |

Followed by [DamageData](B070_SERVER_ENTITY_SKILL_START.md#damagedata-shared-sub-structure) (same sub-structure as SKILL_START).

### Structure Summary

```
  [   0] Success                        bool
  if Success:
    [   1] SkillUniqueID                u32
    [   5] TargetUniqueID               u32
    [   9] DamageData                   (variable)
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A600B` |
| 2 | `wParam` | `u16` | 2 | `0x008A6020` |
| 3 | `byAction` | `bytes` | variable | `0x008A6052` |
| 4 | `dwUniqueID1` | `u32` | 4 | `0x008A6060` |
| 5 | `dwUniqueID2` | `u32` | 4 | `0x008A606E` |
| 6 | `dwTargetUID` | `u32` | 4 | `0x008A607C` |
| 7 | `dwField_07` | `u32` | 4 | `0x00A54C5D` |
| 8 | `byField_08` | `u8` | 1 | `0x00A54C7F` |
| 9 | `byField_09` | `u8` | 1 | `0x00A548F6` |
| 10 | `byField_10` | `u8` | 1 | `0x00A54904` |
| 11 | `dwField_11` | `u32` | 4 | `0x00A54CBB` |
| 12 | `wField_12` | `u16` | 2 | `0x00A54D1F` |
| 13 | `bytesData_12` | `bytes[12]` | 12 | `0x00A54D2D` |
| 14 | `bytesData_13` | `bytes` | variable | `0x00A54E02` |
| 15 | `bytesData_14` | `bytes[12]` | 12 | `0x00A54E10` |
| 16 | `bytesData_15` | `bytes` | variable | `0x008416B1` |
| 17 | `bytesData_16` | `bytes` | variable | `0x00841948` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>
