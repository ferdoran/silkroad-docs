# SERVER_ENTITY_SPAWN

| Property | Value |
|----------|-------|
| Opcode | `0x303D` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088B200`, `0x008ADD60` |

## Handler 1: `0x0088B200`

### Fields

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
| 16 | `byWalkSpeed` | `u16` | 2 | `0x0088B68C` |
| 17 | `byRunSpeed` | `u8` | 1 | `0x0088B6AA` |
| 18 | `byBerserkSpeed` | `u16` | 2 | `0x0088B6D7` |
| 19 | `wBuffCount` | `u16` | 2 | `0x0088B728` |
| 20 | `bytesName` | `u8` | 1 | `0x006FAFA8` |
| 21 | `bytesGuildName` | `u8` | 1 | `0x006FB03E` |
| 22 | `byJobType` | `bytes` | variable | `0x006FB086` |
| 23 | `byJobLevel` | `bytes[12]` | 12 | `0x006FB0A0` |
| 24 | `byPKFlag` | `u8` | 1 | `0x0088B81B` |
| 25 | `byBerserkFlag` | `u8` | 1 | `0x0088B831` |
| 26 | `byField_26` | `u8` | 1 | `0x0088B83F` |

**Minimum size**: 47 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `STORE_TOMB_GATE_IN` | Debug |
| `STORE_DESERT_MERCHANT_HUNTER_GATE` | Debug |
| `STORE_DESERT_THIEF_GATE` | Debug |
| `INS_TEMPLE_SETH_TELEPORT` | Debug |
| `!(byMask & VITAL_INFO_MP)` | Debug |
| `!(byMask & VITAL_INFO_ABNORMAL)` | Debug |
| `UIIT_MSG_STRGERR_CANT_SWAP_JOBITEM` | UI |


### String References
| String | Type |
|--------|------|
| `d:\\vss-od\\silkroad\\client\\client\\MsgStreamBuffer.h` | Debug |

### Structure Summary

```
  [   0] byEntityType                   u8
  [   1] dwRefObjID                     u32
  [   5] bySpecialType                  u8
  [   6] dwUniqueID                     u32
  [  10] wRegionID                      u8
  [  11] fPosX                          u8
  [  12] fPosY                          u8
  [  13] fPosZ                          u8
  [  14] wAngle                         u8
  [  15] byMoving                       u16
  [  17] byRunning                      u16
  [  19] wDestRegion                    u8
  [  20] wDestX                         u8
  [  21] wDestZ                         u8
  [  22] byLifeState                    u8
  [  23] byWalkSpeed                    u16
  [  25] byRunSpeed                     u8
  [  26] byBerserkSpeed                 u16
  [  28] wBuffCount                     u16
  [  30] bytesName                      u8
  [  31] bytesGuildName                 u8
  [  32] byJobType                      bytes  (variable length)
  [   0] byJobLevel                     bytes[12]
  [  12] byPKFlag                       u8
  [  13] byBerserkFlag                  u8
  [  14] byField_26                     u8
```

## Handler 2: `0x008ADD60`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byEntityType` | `u32` | 4 | `0x008ADD94` |
| 2 | `dwRefObjID` | `u32` | 4 | `0x008ADE07` |
| 3 | `bySpecialType` | `u16` | 2 | `0x008ADE15` |
| 4 | `dwUniqueID` | `u16` | 2 | `0x008ADE23` |
| 5 | `wRegionID` | `bytes` | variable | `0x004F71C5` |

**Minimum size**: 12 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `STORE_TOMB_GATE_IN` | Debug |
| `STORE_DESERT_MERCHANT_HUNTER_GATE` | Debug |
| `STORE_DESERT_THIEF_GATE` | Debug |
| `INS_TEMPLE_SETH_TELEPORT` | Debug |
| `!(byMask & VITAL_INFO_MP)` | Debug |
| `!(byMask & VITAL_INFO_ABNORMAL)` | Debug |
| `UIIT_MSG_STRGERR_CANT_SWAP_JOBITEM` | UI |


### String References
| String | Type |
|--------|------|
| `d:\\vss-od\\silkroad\\client\\client\\MsgStreamBuffer.h` | Debug |

### Structure Summary

```
  [   0] byEntityType                   u32
  [   4] dwRefObjID                     u32
  [   8] bySpecialType                  u16
  [  10] dwUniqueID                     u16
  [  12] wRegionID                      bytes  (variable length)
```
