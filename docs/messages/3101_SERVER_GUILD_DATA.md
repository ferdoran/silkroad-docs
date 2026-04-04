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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildData {
        uint32_t GuildID;
        std::string GuildName;
        uint8_t GuildLevel;
        uint32_t GuildPoints;
        std::string Notice;
        std::string Message;
        uint32_t UnionID;  // conditional
        uint8_t StorageSlots;
        uint8_t MemberCount;
        uint32_t MemberID;
        std::string MemberName;
        uint8_t Authority;
        uint8_t Level;
        uint32_t Contribution;
        uint32_t PermissionsFlags;
        uint32_t GP_Donation;
        uint32_t GuildWarKillCount;
        uint32_t SiegeAuthority;
        std::string Nickname;
        uint32_t ModelID;
        bool IsMaster;
        bool IsOffline;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildData(
        uint GuildID,
        string GuildName,
        byte GuildLevel,
        uint GuildPoints,
        string Notice,
        string Message,
        uint UnionID /* conditional */,
        byte StorageSlots,
        byte MemberCount,
        uint MemberID,
        string MemberName,
        byte Authority,
        byte Level,
        uint Contribution,
        uint PermissionsFlags,
        uint GP_Donation,
        uint GuildWarKillCount,
        uint SiegeAuthority,
        string Nickname,
        uint ModelID,
        bool IsMaster,
        bool IsOffline
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildData {
        pub guild_id: u32,
        pub guild_name: String,
        pub guild_level: u8,
        pub guild_points: u32,
        pub notice: String,
        pub message: String,
        pub union_id: u32,  // conditional
        pub storage_slots: u8,
        pub member_count: u8,
        pub member_id: u32,
        pub member_name: String,
        pub authority: u8,
        pub level: u8,
        pub contribution: u32,
        pub permissions_flags: u32,
        pub gp_donation: u32,
        pub guild_war_kill_count: u32,
        pub siege_authority: u32,
        pub nickname: String,
        pub model_id: u32,
        pub is_master: bool,
        pub is_offline: bool,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildData struct {
        GuildID uint32
        GuildName string
        GuildLevel uint8
        GuildPoints uint32
        Notice string
        Message string
        UnionID uint32  // conditional
        StorageSlots uint8
        MemberCount uint8
        MemberID uint32
        MemberName string
        Authority uint8
        Level uint8
        Contribution uint32
        PermissionsFlags uint32
        GP_Donation uint32
        GuildWarKillCount uint32
        SiegeAuthority uint32
        Nickname string
        ModelID uint32
        IsMaster bool
        IsOffline bool
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildData {
        guildID: number;
        guildName: string;
        guildLevel: number;
        guildPoints: number;
        notice: string;
        message: string;
        unionID: number;  // conditional
        storageSlots: number;
        memberCount: number;
        memberID: number;
        memberName: string;
        authority: number;
        level: number;
        contribution: number;
        permissionsFlags: number;
        gP_Donation: number;
        guildWarKillCount: number;
        siegeAuthority: number;
        nickname: string;
        modelID: number;
        isMaster: boolean;
        isOffline: boolean;
    }
    ```

