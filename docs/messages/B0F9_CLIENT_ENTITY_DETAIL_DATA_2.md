# CLIENT_ENTITY_DETAIL_DATA_2
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0F9` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00887300` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088737B` |
| 2 | `dwGuildID` | `u32` | 4 | `0x0088753B` |
| 3 | `byRace` | `u16` | 2 | `0x004F7A7D` |
| 4 | `byLevel` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwGP1` | `u8` | 1 | `0x00887558` |
| 6 | `dwGP2` | `u8` | 1 | `0x00887566` |
| 7 | `dwGP3` | `u32` | 4 | `0x00887574` |
| 8 | `dwGP4` | `u32` | 4 | `0x00887582` |
| 9 | `dwGoldStored` | `u32` | 4 | `0x00887590` |
| 10 | `dwGoldLimit` | `u32` | 4 | `0x0088759E` |
| 11 | `byMemberCount` | `u32` | 4 | `0x008875AC` |
| 12 | `byMemberFlags` | `u32` | 4 | `0x008875C9` |
| 13 | `dwMemberData` | `u8` | 1 | `0x008875D7` |
| 14 | `byMemberRole` | `u8` | 1 | `0x008875E5` |
| 15 | `dwMemberParam` | `u32` | 4 | `0x00887747` |
| 16 | `byMemberLevel` | `u8` | 1 | `0x00887807` |
| 17 | `byMemberExtra1` | `u32` | 4 | `0x008879DC` |
| 18 | `dwMemberUID` | `u8` | 1 | `0x008879EA` |
| 19 | `dwMemberAssoc` | `u8` | 1 | `0x005BB24E` |
| 20 | `byFlagByte1` | `u8` | 1 | `0x005BB276` |
| 21 | `byFlagByte2` | `u8` | 1 | `0x005BB683` |
| 22 | `dwExtraUID` | `u32` | 4 | `0x005BB86D` |
| 23 | `dwExtraParam1` | `u32` | 4 | `0x005BB890` |
| 24 | `byExtraFlags` | `u8` | 1 | `0x00887A1A` |
| 25 | `dwExtraParam2` | `u32` | 4 | `0x00887A39` |
| 26 | `byExtraRole` | `u32` | 4 | `0x00887A47` |
| 27 | `byField_27` | `u8` | 1 | `0x00887A75` |

**Minimum size**: 66 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_CTL_MASTERRELEASE_NOTICE` | UI |

### Structure Summary

```
  [   0] byType                         u8
  [   1] dwGuildID                      u32
  [   5] byRace                         u16
  [   7] byLevel                        bytes  (variable length)
  [   0] dwGP1                          u8
  [   1] dwGP2                          u8
  [   2] dwGP3                          u32
  [   6] dwGP4                          u32
  [  10] dwGoldStored                   u32
  [  14] dwGoldLimit                    u32
  [  18] byMemberCount                  u32
  [  22] byMemberFlags                  u32
  [  26] dwMemberData                   u8
  [  27] byMemberRole                   u8
  [  28] dwMemberParam                  u32
  [  32] byMemberLevel                  u8
  [  33] byMemberExtra1                 u32
  [  37] dwMemberUID                    u8
  [  38] dwMemberAssoc                  u8
  [  39] byFlagByte1                    u8
  [  40] byFlagByte2                    u8
  [  41] dwExtraUID                     u32
  [  45] dwExtraParam1                  u32
  [  49] byExtraFlags                   u8
  [  50] dwExtraParam2                  u32
  [  54] byExtraRole                    u32
  [  58] byField_27                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityDetailData2 {
        uint8_t byType;
        uint32_t dwGuildID;
        uint16_t byRace;
        std::vector<uint8_t> byLevel;
        uint8_t dwGP1;
        uint8_t dwGP2;
        uint32_t dwGP3;
        uint32_t dwGP4;
        uint32_t dwGoldStored;
        uint32_t dwGoldLimit;
        uint32_t byMemberCount;
        uint32_t byMemberFlags;
        uint8_t dwMemberData;
        uint8_t byMemberRole;
        uint32_t dwMemberParam;
        uint8_t byMemberLevel;
        uint32_t byMemberExtra1;
        uint8_t dwMemberUID;
        uint8_t dwMemberAssoc;
        uint8_t byFlagByte1;
        uint8_t byFlagByte2;
        uint32_t dwExtraUID;
        uint32_t dwExtraParam1;
        uint8_t byExtraFlags;
        uint32_t dwExtraParam2;
        uint32_t byExtraRole;
        uint8_t byField_27;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityDetailData2(
        byte byType,
        uint dwGuildID,
        ushort byRace,
        byte[] byLevel,
        byte dwGP1,
        byte dwGP2,
        uint dwGP3,
        uint dwGP4,
        uint dwGoldStored,
        uint dwGoldLimit,
        uint byMemberCount,
        uint byMemberFlags,
        byte dwMemberData,
        byte byMemberRole,
        uint dwMemberParam,
        byte byMemberLevel,
        uint byMemberExtra1,
        byte dwMemberUID,
        byte dwMemberAssoc,
        byte byFlagByte1,
        byte byFlagByte2,
        uint dwExtraUID,
        uint dwExtraParam1,
        byte byExtraFlags,
        uint dwExtraParam2,
        uint byExtraRole,
        byte byField_27
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityDetailData2 {
        pub by_type: u8,
        pub dw_guild_id: u32,
        pub by_race: u16,
        pub by_level: Vec<u8>,
        pub dw_gp1: u8,
        pub dw_gp2: u8,
        pub dw_gp3: u32,
        pub dw_gp4: u32,
        pub dw_gold_stored: u32,
        pub dw_gold_limit: u32,
        pub by_member_count: u32,
        pub by_member_flags: u32,
        pub dw_member_data: u8,
        pub by_member_role: u8,
        pub dw_member_param: u32,
        pub by_member_level: u8,
        pub by_member_extra1: u32,
        pub dw_member_uid: u8,
        pub dw_member_assoc: u8,
        pub by_flag_byte1: u8,
        pub by_flag_byte2: u8,
        pub dw_extra_uid: u32,
        pub dw_extra_param1: u32,
        pub by_extra_flags: u8,
        pub dw_extra_param2: u32,
        pub by_extra_role: u32,
        pub by_field_27: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityDetailData2 struct {
        byType uint8
        dwGuildID uint32
        byRace uint16
        byLevel []byte
        dwGP1 uint8
        dwGP2 uint8
        dwGP3 uint32
        dwGP4 uint32
        dwGoldStored uint32
        dwGoldLimit uint32
        byMemberCount uint32
        byMemberFlags uint32
        dwMemberData uint8
        byMemberRole uint8
        dwMemberParam uint32
        byMemberLevel uint8
        byMemberExtra1 uint32
        dwMemberUID uint8
        dwMemberAssoc uint8
        byFlagByte1 uint8
        byFlagByte2 uint8
        dwExtraUID uint32
        dwExtraParam1 uint32
        byExtraFlags uint8
        dwExtraParam2 uint32
        byExtraRole uint32
        byField_27 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityDetailData2 {
        byType: number;
        dwGuildID: number;
        byRace: number;
        byLevel: Uint8Array;
        dwGP1: number;
        dwGP2: number;
        dwGP3: number;
        dwGP4: number;
        dwGoldStored: number;
        dwGoldLimit: number;
        byMemberCount: number;
        byMemberFlags: number;
        dwMemberData: number;
        byMemberRole: number;
        dwMemberParam: number;
        byMemberLevel: number;
        byMemberExtra1: number;
        dwMemberUID: number;
        dwMemberAssoc: number;
        byFlagByte1: number;
        byFlagByte2: number;
        dwExtraUID: number;
        dwExtraParam1: number;
        byExtraFlags: number;
        dwExtraParam2: number;
        byExtraRole: number;
        byField_27: number;
    }
    ```

