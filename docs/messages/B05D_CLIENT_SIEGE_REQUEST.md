# CLIENT_SIEGE_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0xB05D` |
| Direction | Client → Server |
| Group | Game (Client→Server) |
| Handler(s) | `0x00895BB0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x00895BFB` |
| 2 | `bySubType` | `u8` | 1 | `0x00895C25` |
| 3 | `dwGuildID` | `u32` | 4 | `0x00895CCE` |
| 4 | `dwParam1` | `u16` | 2 | `0x004F7A7D` |
| 5 | `dwParam2` | `bytes` | variable | `0x004F7AB9` |
| 6 | `dwParam3` | `u32` | 4 | `0x00895CEE` |
| 7 | `dwParam4` | `u32` | 4 | `0x00895D1D` |
| 8 | `byFlags` | `u32` | 4 | `0x00895D2E` |
| 9 | `dwTargetID` | `u32` | 4 | `0x00895D3F` |
| 10 | `byConfirm` | `u8` | 1 | `0x00895D4D` |
| 11 | `dwValue` | `u32` | 4 | `0x00895D8B` |
| 12 | `byExtra` | `u8` | 1 | `0x00895D99` |
| 13 | `dwExtraParam` | `u32` | 4 | `0x00895DAE` |
| 14 | `byField_14` | `u8` | 1 | `0x00895EA3` |
| 15 | `dwField_15` | `u32` | 4 | `0x00895EC2` |

**Minimum size**: 39 bytes + variable fields


### String References
| String | Type |
|--------|------|
| `[Debug] FORTRESS STATE : SIEGE_DEFAULT_PERIOD` | Debug |
| `[Debug] FORTRESS STATE : SIEGE_WAR` | Debug |
| `[Debug] FORTRESS STATE : SIEGE_REQUEST_ALLOWED_PERIOD` | Debug |
| `[Debug] FORTRESS STATE : SIEGE_TAX_ALLOWED_PERIOD` | Debug |
| `fortress_war.ogg` | Debug |
| `[Debug] 수성길드가 없습니다.` | Debug |
| `[Debug] 당신의 길드가 없습니다 따라서 요새전과 관련이 없습니다.` | Debug |
| `[Debug] 당신의 길드는 수성입니다` | Debug |
| `[Debug] 세금징수 기간이 시작되었습니다.` | Debug |
| `[Debug] 요새전 신청 기간이 시작되었습니다.` | Debug |
| `UIIT_MSG_FORT_WAR_BEFOREBEGIN` | UI |
| `UIIT_MSG_FORT_WAR_BEGIN` | UI |
| `UIIT_MSG_FORT_WAR_BEFOREEND` | UI |
| `UIIT_MSG_FORT_WAR_CONQUER` | UI |
| `UIIT_MSG_FORT_STRUCTURE_STATUS_CANCEL` | UI |
| `UIIT_MSG_FORT_CAMP_STATUS_DESTROY` | UI |
| `UIIT_MSG_FORT_OFFICIAL_WARAPPLY_COMPLETE` | UI |
| `UIIT_MSG_FORT_OFFICIAL_WARAPPLY_CANCEL` | UI |
| `UIIT_MSG_FORT_OFFICIAL_UNIONAPPLY_CANCEL` | UI |
| `UIIT_MSG_FORT_BATTLERANK_GRANT` | UI |
| `UIIT_STT_FORT_REWARD_MESSAGE_MASTER` | UI |
| `UIIT_MSG_FORTRESS_DUNGEON_CREATE_COMPLATE_MSG` | UI |
| `UIIT_MSG_FORTRESS_DUNGEON_CLOSE_COMPLATE_MSG` | UI |

### Structure Summary

```
  [   0] byType                         u8
  [   1] bySubType                      u8
  [   2] dwGuildID                      u32
  [   6] dwParam1                       u16
  [   8] dwParam2                       bytes  (variable length)
  [   0] dwParam3                       u32
  [   4] dwParam4                       u32
  [   8] byFlags                        u32
  [  12] dwTargetID                     u32
  [  16] byConfirm                      u8
  [  17] dwValue                        u32
  [  21] byExtra                        u8
  [  22] dwExtraParam                   u32
  [  26] byField_14                     u8
  [  27] dwField_15                     u32
```
