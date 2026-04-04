# CLIENT_SIEGE_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB05D` |
| Direction | Server → Client |
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

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct SiegeRequest {
        uint8_t byType;
        uint8_t bySubType;
        uint32_t dwGuildID;
        uint16_t dwParam1;
        std::vector<uint8_t> dwParam2;
        uint32_t dwParam3;
        uint32_t dwParam4;
        uint32_t byFlags;
        uint32_t dwTargetID;
        uint8_t byConfirm;
        uint32_t dwValue;
        uint8_t byExtra;
        uint32_t dwExtraParam;
        uint8_t byField_14;
        uint32_t dwField_15;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record SiegeRequest(
        byte byType,
        byte bySubType,
        uint dwGuildID,
        ushort dwParam1,
        byte[] dwParam2,
        uint dwParam3,
        uint dwParam4,
        uint byFlags,
        uint dwTargetID,
        byte byConfirm,
        uint dwValue,
        byte byExtra,
        uint dwExtraParam,
        byte byField_14,
        uint dwField_15
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct SiegeRequest {
        pub by_type: u8,
        pub by_sub_type: u8,
        pub dw_guild_id: u32,
        pub dw_param1: u16,
        pub dw_param2: Vec<u8>,
        pub dw_param3: u32,
        pub dw_param4: u32,
        pub by_flags: u32,
        pub dw_target_id: u32,
        pub by_confirm: u8,
        pub dw_value: u32,
        pub by_extra: u8,
        pub dw_extra_param: u32,
        pub by_field_14: u8,
        pub dw_field_15: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type SiegeRequest struct {
        byType uint8
        bySubType uint8
        dwGuildID uint32
        dwParam1 uint16
        dwParam2 []byte
        dwParam3 uint32
        dwParam4 uint32
        byFlags uint32
        dwTargetID uint32
        byConfirm uint8
        dwValue uint32
        byExtra uint8
        dwExtraParam uint32
        byField_14 uint8
        dwField_15 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface SiegeRequest {
        byType: number;
        bySubType: number;
        dwGuildID: number;
        dwParam1: number;
        dwParam2: Uint8Array;
        dwParam3: number;
        dwParam4: number;
        byFlags: number;
        dwTargetID: number;
        byConfirm: number;
        dwValue: number;
        byExtra: number;
        dwExtraParam: number;
        byField_14: number;
        dwField_15: number;
    }
    ```

