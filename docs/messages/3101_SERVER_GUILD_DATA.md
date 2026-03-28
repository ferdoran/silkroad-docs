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
| 7 | `UnionID` | `u32` | 4 | Alliance/union guild ID (0 if none) |
| 8 | `StorageSlots` | `u8` | 1 | Number of guild storage slots |
| 9 | `MemberCount` | `u8` | 1 | Number of guild members |

For each member:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| - | `MemberID` | `u32` | 4 | Character DB ID |
| - | `MemberName` | `ascii` | var | Character name |
| - | `Authority` | `u8` | 1 | Member rank/authority (0=Master, 1=Officer, 2=Member) — `GUILD_MEMBER_INFO.Permission` |
| - | `Level` | `u8` | 1 | Character level |
| - | `Contribution` | `u32` | 4 | Member contribution points — `GUILD_MEMBER_INFO.Contribution` |
| - | `PermissionsFlags` | `u32` | 4 | Guild permission bitmask — `GUILD_MEMBER_INFO.Permission` |
| - | `GP_Donation` | `u32` | 4 | Guild points donated by member — `GUILD_MEMBER_INFO.GP_Donation` |
| - | `GuildWarKillCount` | `u32` | 4 | Kills in guild war — `GUILD_MEMBER_INFO.GuildWarKill` |
| - | `SiegeAuthority` | `u32` | 4 | Siege authorization flags — `GUILD_MEMBER_INFO.SiegeAuthority` |
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
  [   ?] UnionID                        u32       // 0 if no alliance
  [   ?] StorageSlots                   u8
  [   ?] MemberCount                    u8
  for each member:
    MemberID                            u32
    MemberName                          ascii
    Authority                           u8        // GUILD_MEMBER_INFO.Permission rank
    Level                               u8
    Contribution                        u32       // GUILD_MEMBER_INFO.Contribution
    PermissionsFlags                    u32
    GP_Donation                         u32       // GUILD_MEMBER_INFO.GP_Donation
    GuildWarKillCount                   u32       // GUILD_MEMBER_INFO.GuildWarKill
    SiegeAuthority                      u32       // GUILD_MEMBER_INFO.SiegeAuthority
    Nickname                            ascii
    ModelID                             u32
    IsMaster                            bool
    IsOffline                           bool
```
