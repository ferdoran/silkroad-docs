# SERVER_PARTY_DATA

> Source: Server binary reverse engineering. See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3065` |
| Direction | Server → Client |
| Group | Game (Server→Client) |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `PartyID` | `u32` | 4 | Party unique ID |
| 2 | `LeaderJoinID` | `u32` | 4 | JoinID of the party leader |
| 3 | `PurposeType` | `u8` | 1 | Party purpose |
| 4 | `SetupFlags` | `u8` | 1 | Party configuration flags |
| 5 | `PlayerCount` | `u8` | 1 | Number of members |

For each member: [PartyMemberData](#partymemberdata-shared-sub-structure)

### PartyMemberData (shared sub-structure)

Used by both SERVER_PARTY_DATA and [SERVER_PARTY_UPDATE](3864_SERVER_PARTY_UPDATE.md).

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `MemberType` | `u8` | 1 | Member role type (0=normal member) |
| 2 | `MemberID` | `u32` | 4 | JoinID |
| 3 | `Name` | `ascii` | var | Character name |
| 4 | `ModelID` | `u32` | 4 | RefObjID |
| 5 | `Level` | `u8` | 1 | Character level |
| 6 | `HPMP` | `u8` | 1 | Packed: HP% in high nibble, MP% in low nibble |
| 7 | `RegionID` | `u16` | 2 | Map region |
| 8 | `PosX` | `u16/i32` | 2/4 | X coordinate (i32 if dungeon, u16 otherwise) |
| 9 | `PosY` | `u16/i32` | 2/4 | Y coordinate |
| 10 | `PosZ` | `u16/i32` | 2/4 | Z coordinate |
| 11 | `BodyMode` | `u8` | 1 | `BODYMODE_*` enum — from `BUF_CHARACTER_STATUS` RTTI |
| 12 | `LifeState` | `u8` | 1 | `LIFESTATE_*` enum — from `BUF_CHARACTER_STATUS` RTTI |
| 13 | `MotionState` | `u8` | 1 | `MOTIONSTATE_*` enum — from `BUF_CHARACTER_STATUS` RTTI |
| 14 | `BattleState` | `u8` | 1 | `BATTLESTATE_*` enum — from `BUF_CHARACTER_STATUS` RTTI |
| 15 | `GuildName` | `ascii` | var | Guild name |
| 16 | `GuildAuthority` | `u8` | 1 | Guild member authority level — from `GUILD_MEMBER_INFO.Permission` RTTI |
| 17 | `MasteryPrimaryID` | `u32` | 4 | Primary mastery |
| 18 | `MasterySecondaryID` | `u32` | 4 | Secondary mastery |

### Structure Summary

```
  [   0] PartyID                        u32
  [   4] LeaderJoinID                   u32
  [   8] PurposeType                    u8
  [   9] SetupFlags                     u8
  [  10] PlayerCount                    u8
  for each member:
    MemberType                          u8
    MemberID                            u32
    Name                                ascii
    ModelID                             u32
    Level                               u8
    HPMP                                u8        // packed HP%/MP%
    RegionID                            u16
    if inDungeon: i32 PosX/Y/Z
    else: u16 PosX/Y/Z
    BodyMode                            u8        // BODYMODE_*
    LifeState                           u8        // LIFESTATE_*
    MotionState                         u8        // MOTIONSTATE_*
    BattleState                         u8        // BATTLESTATE_*
    GuildName                           ascii
    GuildAuthority                      u8        // GUILD_MEMBER_INFO.Permission
    MasteryPrimaryID                    u32
    MasterySecondaryID                  u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyData {
        uint32_t PartyID;
        uint32_t LeaderJoinID;
        uint8_t PurposeType;
        uint8_t SetupFlags;
        uint8_t PlayerCount;
        uint8_t MemberType;
        uint32_t MemberID;
        std::string Name;
        uint32_t ModelID;
        uint8_t Level;
        uint8_t HPMP;
        uint16_t RegionID;
        uint16_t PosX;  // conditional
        uint16_t PosY;
        uint16_t PosZ;
        uint8_t BodyMode;
        uint8_t LifeState;
        uint8_t MotionState;
        uint8_t BattleState;
        std::string GuildName;
        uint8_t GuildAuthority;
        uint32_t MasteryPrimaryID;
        uint32_t MasterySecondaryID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyData(
        uint PartyID,
        uint LeaderJoinID,
        byte PurposeType,
        byte SetupFlags,
        byte PlayerCount,
        byte MemberType,
        uint MemberID,
        string Name,
        uint ModelID,
        byte Level,
        byte HPMP,
        ushort RegionID,
        ushort PosX /* conditional */,
        ushort PosY,
        ushort PosZ,
        byte BodyMode,
        byte LifeState,
        byte MotionState,
        byte BattleState,
        string GuildName,
        byte GuildAuthority,
        uint MasteryPrimaryID,
        uint MasterySecondaryID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyData {
        pub party_id: u32,
        pub leader_join_id: u32,
        pub purpose_type: u8,
        pub setup_flags: u8,
        pub player_count: u8,
        pub member_type: u8,
        pub member_id: u32,
        pub name: String,
        pub model_id: u32,
        pub level: u8,
        pub hpmp: u8,
        pub region_id: u16,
        pub pos_x: u16,  // conditional
        pub pos_y: u16,
        pub pos_z: u16,
        pub body_mode: u8,
        pub life_state: u8,
        pub motion_state: u8,
        pub battle_state: u8,
        pub guild_name: String,
        pub guild_authority: u8,
        pub mastery_primary_id: u32,
        pub mastery_secondary_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyData struct {
        PartyID uint32
        LeaderJoinID uint32
        PurposeType uint8
        SetupFlags uint8
        PlayerCount uint8
        MemberType uint8
        MemberID uint32
        Name string
        ModelID uint32
        Level uint8
        HPMP uint8
        RegionID uint16
        PosX uint16  // conditional
        PosY uint16
        PosZ uint16
        BodyMode uint8
        LifeState uint8
        MotionState uint8
        BattleState uint8
        GuildName string
        GuildAuthority uint8
        MasteryPrimaryID uint32
        MasterySecondaryID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyData {
        partyID: number;
        leaderJoinID: number;
        purposeType: number;
        setupFlags: number;
        playerCount: number;
        memberType: number;
        memberID: number;
        name: string;
        modelID: number;
        level: number;
        hPMP: number;
        regionID: number;
        posX: number;  // conditional
        posY: number;
        posZ: number;
        bodyMode: number;
        lifeState: number;
        motionState: number;
        battleState: number;
        guildName: string;
        guildAuthority: number;
        masteryPrimaryID: number;
        masterySecondaryID: number;
    }
    ```

