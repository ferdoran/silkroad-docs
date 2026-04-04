# SERVER_CHARACTER_STATS_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_SPAWN` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x303D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088B200`, `0x008ADD60` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `PhyAtkMin` | `u32` | 4 | Minimum physical attack |
| 2 | `PhyAtkMax` | `u32` | 4 | Maximum physical attack |
| 3 | `MagAtkMin` | `u32` | 4 | Minimum magical attack |
| 4 | `MagAtkMax` | `u32` | 4 | Maximum magical attack |
| 5 | `PhyDefense` | `u16` | 2 | Physical defense |
| 6 | `MagDefense` | `u16` | 2 | Magical defense |
| 7 | `HitRate` | `u16` | 2 | Hit rate |
| 8 | `ParryRatio` | `u16` | 2 | Parry ratio |
| 9 | `HPMax` | `u32` | 4 | Maximum HP |
| 10 | `MPMax` | `u32` | 4 | Maximum MP |
| 11 | `STR` | `u16` | 2 | Strength |
| 12 | `INT` | `u16` | 2 | Intelligence |

**Total size**: 36 bytes

### Structure Summary

```
  [   0] PhyAtkMin                      u32
  [   4] PhyAtkMax                      u32
  [   8] MagAtkMin                      u32
  [  12] MagAtkMax                      u32
  [  16] PhyDefense                     u16
  [  18] MagDefense                     u16
  [  20] HitRate                        u16
  [  22] ParryRatio                     u16
  [  24] HPMax                          u32
  [  28] MPMax                          u32
  [  32] STR                            u16
  [  34] INT                            u16
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

## Handler 1: `0x0088B200`

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byEntityType` | `u8` | 1 | `0x0088B25F` |
| 2 | `dwRefObjID` | `u32` | 4 | `0x0088B286` |
| 3 | `bySpecialType` | `u8` | 1 | `0x0088B37C` |
| 4 | `dwUniqueID` | `u32` | 4 | `0x0088B393` |
| 5 | `wRegionID` | `u8` | 1 | `0x0088B3FB` |
| 6 | `fPosX` | `u8` | 1 | `0x0088B419` |
| 7 | `fPosY` | `u8` | 1 | `0x0088B45B` |
| 8 | `fPosZ` | `u8` | 1 | `0x0088B474` |
| 9 | `wAngle` | `u8` | 1 | `0x0088B4F1` |
| 10 | `byMoving` | `u16` | 2 | `0x0088B562` |
| 11 | `byRunning` | `u16` | 2 | `0x0088B570` |
| 12 | `wDestRegion` | `u8` | 1 | `0x0088B5BD` |
| 13 | `wDestX` | `u8` | 1 | `0x0088B5CB` |
| 14 | `wDestZ` | `u8` | 1 | `0x0088B5FC` |
| 15 | `byLifeState` | `u8` | 1 | `0x0088B619` |
| 16 | `fSpeedWalking` | `u16` | 2 | `0x0088B68C` |
| 17 | `fSpeedRunning` | `u8` | 1 | `0x0088B6AA` |
| 18 | `fSpeedBerserk` | `u16` | 2 | `0x0088B6D7` |
| 19 | `wBuffCount` | `u16` | 2 | `0x0088B728` |
| 20 | `bytesName` | `u8` | 1 | `0x006FAFA8` |
| 21 | `bytesGuildName` | `u8` | 1 | `0x006FB03E` |
| 22 | `byJobType` | `bytes` | variable | `0x006FB086` |
| 23 | `byJobLevel` | `bytes[12]` | 12 | `0x006FB0A0` |
| 24 | `byPVPState` | `u8` | 1 | `0x0088B81B` |
| 25 | `byBerserkLevel` | `u8` | 1 | `0x0088B831` |
| 26 | `byField_26` | `u8` | 1 | `0x0088B83F` |

> Note: Client handler data appears to be from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

## Handler 2: `0x008ADD60`

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byEntityType` | `u32` | 4 | `0x008ADD94` |
| 2 | `dwRefObjID` | `u32` | 4 | `0x008ADE07` |
| 3 | `bySpecialType` | `u16` | 2 | `0x008ADE15` |
| 4 | `dwUniqueID` | `u16` | 2 | `0x008ADE23` |
| 5 | `wRegionID` | `bytes` | variable | `0x004F71C5` |

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterStatsUpdate {
        uint32_t PhyAtkMin;
        uint32_t PhyAtkMax;
        uint32_t MagAtkMin;
        uint32_t MagAtkMax;
        uint16_t PhyDefense;
        uint16_t MagDefense;
        uint16_t HitRate;
        uint16_t ParryRatio;
        uint32_t HPMax;
        uint32_t MPMax;
        uint16_t STR;
        uint16_t INT;
        uint8_t byEntityType;
        uint32_t dwRefObjID;
        uint8_t bySpecialType;
        uint32_t dwUniqueID;
        uint8_t wRegionID;
        uint8_t fPosX;
        uint8_t fPosY;
        uint8_t fPosZ;
        uint8_t wAngle;
        uint16_t byMoving;
        uint16_t byRunning;
        uint8_t wDestRegion;
        uint8_t wDestX;
        uint8_t wDestZ;
        uint8_t byLifeState;
        uint16_t fSpeedWalking;
        uint8_t fSpeedRunning;
        uint16_t fSpeedBerserk;
        uint16_t wBuffCount;
        uint8_t bytesName;
        uint8_t bytesGuildName;
        std::vector<uint8_t> byJobType;
        uint8_t byJobLevel;
        uint8_t byPVPState;
        uint8_t byBerserkLevel;
        uint8_t byField_26;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterStatsUpdate(
        uint PhyAtkMin,
        uint PhyAtkMax,
        uint MagAtkMin,
        uint MagAtkMax,
        ushort PhyDefense,
        ushort MagDefense,
        ushort HitRate,
        ushort ParryRatio,
        uint HPMax,
        uint MPMax,
        ushort STR,
        ushort INT,
        byte byEntityType,
        uint dwRefObjID,
        byte bySpecialType,
        uint dwUniqueID,
        byte wRegionID,
        byte fPosX,
        byte fPosY,
        byte fPosZ,
        byte wAngle,
        ushort byMoving,
        ushort byRunning,
        byte wDestRegion,
        byte wDestX,
        byte wDestZ,
        byte byLifeState,
        ushort fSpeedWalking,
        byte fSpeedRunning,
        ushort fSpeedBerserk,
        ushort wBuffCount,
        byte bytesName,
        byte bytesGuildName,
        byte[] byJobType,
        byte byJobLevel,
        byte byPVPState,
        byte byBerserkLevel,
        byte byField_26
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterStatsUpdate {
        pub phy_atk_min: u32,
        pub phy_atk_max: u32,
        pub mag_atk_min: u32,
        pub mag_atk_max: u32,
        pub phy_defense: u16,
        pub mag_defense: u16,
        pub hit_rate: u16,
        pub parry_ratio: u16,
        pub hpmax: u32,
        pub mpmax: u32,
        pub str: u16,
        pub int: u16,
        pub by_entity_type: u8,
        pub dw_ref_obj_id: u32,
        pub by_special_type: u8,
        pub dw_unique_id: u32,
        pub w_region_id: u8,
        pub f_pos_x: u8,
        pub f_pos_y: u8,
        pub f_pos_z: u8,
        pub w_angle: u8,
        pub by_moving: u16,
        pub by_running: u16,
        pub w_dest_region: u8,
        pub w_dest_x: u8,
        pub w_dest_z: u8,
        pub by_life_state: u8,
        pub f_speed_walking: u16,
        pub f_speed_running: u8,
        pub f_speed_berserk: u16,
        pub w_buff_count: u16,
        pub bytes_name: u8,
        pub bytes_guild_name: u8,
        pub by_job_type: Vec<u8>,
        pub by_job_level: u8,
        pub by_pvpstate: u8,
        pub by_berserk_level: u8,
        pub by_field_26: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterStatsUpdate struct {
        PhyAtkMin uint32
        PhyAtkMax uint32
        MagAtkMin uint32
        MagAtkMax uint32
        PhyDefense uint16
        MagDefense uint16
        HitRate uint16
        ParryRatio uint16
        HPMax uint32
        MPMax uint32
        STR uint16
        INT uint16
        byEntityType uint8
        dwRefObjID uint32
        bySpecialType uint8
        dwUniqueID uint32
        wRegionID uint8
        fPosX uint8
        fPosY uint8
        fPosZ uint8
        wAngle uint8
        byMoving uint16
        byRunning uint16
        wDestRegion uint8
        wDestX uint8
        wDestZ uint8
        byLifeState uint8
        fSpeedWalking uint16
        fSpeedRunning uint8
        fSpeedBerserk uint16
        wBuffCount uint16
        bytesName uint8
        bytesGuildName uint8
        byJobType []byte
        byJobLevel uint8
        byPVPState uint8
        byBerserkLevel uint8
        byField_26 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterStatsUpdate {
        phyAtkMin: number;
        phyAtkMax: number;
        magAtkMin: number;
        magAtkMax: number;
        phyDefense: number;
        magDefense: number;
        hitRate: number;
        parryRatio: number;
        hPMax: number;
        mPMax: number;
        sTR: number;
        iNT: number;
        byEntityType: number;
        dwRefObjID: number;
        bySpecialType: number;
        dwUniqueID: number;
        wRegionID: number;
        fPosX: number;
        fPosY: number;
        fPosZ: number;
        wAngle: number;
        byMoving: number;
        byRunning: number;
        wDestRegion: number;
        wDestX: number;
        wDestZ: number;
        byLifeState: number;
        fSpeedWalking: number;
        fSpeedRunning: number;
        fSpeedBerserk: number;
        wBuffCount: number;
        bytesName: number;
        bytesGuildName: number;
        byJobType: Uint8Array;
        byJobLevel: number;
        byPVPState: number;
        byBerserkLevel: number;
        byField_26: number;
    }
    ```

