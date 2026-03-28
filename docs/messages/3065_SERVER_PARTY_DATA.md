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
