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
