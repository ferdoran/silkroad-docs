# SERVER_PARTY_UPDATE

> **Corrected name** (server RE): Was `SERVER_WORLD_UPDATE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3864` |
| Direction | Server → Client |
| Group | Game Extended 8 |
| Handler(s) | `0x00880010`, `0x00886B10` |

### Fields (Server RE)

Switched structure based on `UpdateType`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UpdateType` | `u8` | 1 | Type of party update |

**UpdateType values:**

| UpdateType | Description | Payload |
|------------|-------------|---------|
| 1 | Party dismissed | (none, possibly `u16 ErrorCode`) |
| 2 | Member joined | [PartyMemberData](3065_SERVER_PARTY_DATA.md#partymemberdata-shared-sub-structure) |
| 3 | Member left | `u32 MemberID` (possibly + `u8 Reason`) |
| 6 | Member update | See below |

#### UpdateType 6 — Member Update

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 2 | `MemberID` | `u32` | 4 | JoinID of member |
| 3 | `MemberUpdateType` | `u8` | 1 | Sub-update type |

**MemberUpdateType values:**

| MemberUpdateType | Payload | Description |
|------------------|---------|-------------|
| 2 | `u8 Level` | Level changed |
| 4 | `u8 HPMP` | HP/MP percentages (packed nibbles) |
| 0x20 | `u16 RegionID` + coords | Map position update |

Position coords: if `inDungeon(RegionID)`: `i32 PosX/Y/Z`, else `u16 PosX/Y/Z`

### Structure Summary

```
  [   0] UpdateType                     u8
  switch UpdateType:
    case 1: (dismissed)
    case 2:
      [   1] PartyMemberData            (variable)
    case 3:
      [   1] MemberID                   u32
    case 6:
      [   1] MemberID                   u32
      [   5] MemberUpdateType           u8
      switch MemberUpdateType:
        case 2:  [6] Level              u8
        case 4:  [6] HPMP              u8
        case 0x20:
          [   6] RegionID               u16
          if inDungeon: i32 PosX/Y/Z
          else: u16 PosX/Y/Z
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

## Handler 1: `0x00880010`

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088001F` |
| 2 | `dwField_02` | `u32` | 4 | `0x00880054` |

## Handler 2: `0x00886B10`

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00886B5B` |
| 2-24 | (24 fields) | various | — | See client binary analysis |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>
