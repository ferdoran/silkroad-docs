# SERVER_GUILD_DATA

> **Corrected name** (server RE): Was `SERVER_NOTICE_CLEAR` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3101` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00883060` |
| Multi-part | Via `0x34B3` begin / `0x34B4` end |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `GuildID` | `u32` | 4 | Guild unique ID |
| 2 | `GuildName` | `ascii` | var | Guild name |
| 3 | `GuildLevel` | `u8` | 1 | Guild level |
| 4 | `GuildPoints` | `u32` | 4 | Total guild points |
| 5 | `Notice` | `ascii` | var | Guild notice/announcement |
| 6 | `Message` | `ascii` | var | Guild message |
| 7 | `unkUInt00` | `u32` | 4 | Possibly UnionID/AllianceID |
| 8 | `unkByte00` | `u8` | 1 | Possibly GuildStorageSlots |
| 9 | `MemberCount` | `u8` | 1 | Number of guild members |

For each member:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `MemberID` | `u32` | 4 | Character DB ID |
| - | `MemberName` | `ascii` | var | Character name |
| - | `unkByte01` | `u8` | 1 | Possibly MemberAuthority or online flag |
| - | `Level` | `u8` | 1 | Character level |
| - | `GuildPoints` | `u32` | 4 | Member contribution points |
| - | `PermissionsFlags` | `u32` | 4 | Guild permission bitmask |
| - | `unkUInt01` | `u32` | 4 | Possibly LastLoginTime |
| - | `unkUInt02` | `u32` | 4 | Possibly DonateGP |
| - | `unkUInt03` | `u32` | 4 | Possibly CharDBID |
| - | `Nickname` | `ascii` | var | Guild nickname (GetNickName()) |
| - | `ModelID` | `u32` | 4 | RefObjID |
| - | `IsMaster` | `bool` | 1 | Is guild master |
| - | `IsOffline` | `bool` | 1 | Is currently offline |

### Structure Summary

```
  [   0] GuildID                        u32
  [   4] GuildName                      ascii
  [   ?] GuildLevel                     u8
  [   ?] GuildPoints                    u32
  [   ?] Notice                         ascii
  [   ?] Message                        ascii
  [   ?] unkUInt00                      u32       // UnionID?
  [   ?] unkByte00                      u8        // StorageSlots?
  [   ?] MemberCount                    u8
  for each member:
    MemberID                            u32
    MemberName                          ascii
    unkByte01                           u8        // Authority?
    Level                               u8
    GuildPoints                         u32       // contribution
    PermissionsFlags                    u32
    unkUInt01                           u32       // LastLogin?
    unkUInt02                           u32       // DonateGP?
    unkUInt03                           u32       // CharDBID?
    Nickname                            ascii
    ModelID                             u32
    IsMaster                            bool
    IsOffline                           bool
```
