# SERVER_ENTITY_STATS
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3078` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00878B40` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byStatType` | `u8` | 1 | `0x00878BA4` |
| 2 | `byAction` | `u8` | 1 | `0x00878BB2` |
| 3 | `wMinPhyAtk` | `u16` | 2 | `0x00878BC8` |
| 4 | `dwMaxPhyAtk` | `u32` | 4 | `0x004F74CA` |
| 5 | `wMinMagAtk` | `u16` | 2 | `0x004F744A` |
| 6 | `ullHP` | `u64` | 8 | `0x005E8BDA` |
| 7 | `byStr` | `u8` | 1 | `0x004F746A` |
| 8 | `byInt` | `u8` | 1 | `0x00878D91` |
| 9 | `byStatPoint_01` | `u8` | 1 | `0x00878DAB` |
| 10 | `byStatPoint_02` | `u8` | 1 | `0x00878DC5` |
| 11 | `byStatPoint_03` | `u8` | 1 | `0x00878DDF` |
| 12 | `byStatPoint_04` | `u8` | 1 | `0x00878DF9` |
| 13 | `byStatPoint_05` | `u8` | 1 | `0x00878E13` |
| 14 | `byStatPoint_06` | `u8` | 1 | `0x00878E2D` |
| 15 | `byStatPoint_07` | `u8` | 1 | `0x00878E47` |
| 16 | `byStatPoint_08` | `u8` | 1 | `0x00878E61` |
| 17 | `byStatPoint_09` | `u8` | 1 | `0x00878E7B` |
| 18 | `byStatPoint_10` | `u8` | 1 | `0x00878EA8` |
| 19 | `byStatPoint_11` | `u8` | 1 | `0x00878EC2` |
| 20 | `byStatPoint_12` | `u8` | 1 | `0x00878EDC` |
| 21 | `byStatPoint_13` | `u8` | 1 | `0x00878EF6` |
| 22 | `byStatPoint_14` | `u8` | 1 | `0x00878F10` |
| 23 | `byStatPoint_15` | `u8` | 1 | `0x00878F2A` |
| 24 | `byStatPoint_16` | `u8` | 1 | `0x00878F44` |
| 25 | `byStatPoint_17` | `u8` | 1 | `0x00878F5E` |
| 26 | `byStatPoint_18` | `u8` | 1 | `0x00878F78` |
| 27 | `byStatPoint_19` | `u8` | 1 | `0x00878F92` |
| 28 | `byStatPoint_20` | `u8` | 1 | `0x00878FAC` |
| 29 | `byStatPoint_21` | `u8` | 1 | `0x00878FC6` |
| 30 | `byStatPoint_22` | `u8` | 1 | `0x00878FE0` |
| 31 | `byStatPoint_23` | `u8` | 1 | `0x00878FFA` |
| 32 | `byStatPoint_24` | `u8` | 1 | `0x00879014` |
| 33 | `byStatPoint_25` | `u8` | 1 | `0x0087902E` |
| 34 | `byStatPoint_26` | `u16` | 2 | `0x004F74AA` |

**Total size**: 47 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_FORT_MANAGER_TAXLEVY_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_CONSTRUCTION_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_UPGRADE_COMPLETE` | UI |
| `UIIT_MSG_FORT_BATTLEAIDE_REPAIR_COMPLETE` | UI |
| `UIIT_MSG_FORT_COMMON_DISMISS_COMPLETE` | UI |
| `UIIT_MSG_GUILD_INTRODUCE_CHANGE` | UI |
| `UIIT_MSG_FORTRESS_BUFF` | UI |

### Structure Summary

```
  [   0] byStatType                     u8
  [   1] byAction                       u8
  [   2] wMinPhyAtk                     u16
  [   4] dwMaxPhyAtk                    u32
  [   8] wMinMagAtk                     u16
  [  10] ullHP                          u64
  [  18] byStr                          u8
  [  19] byInt                          u8
  [  20] byStatPoint_01                 u8
  [  21] byStatPoint_02                 u8
  [  22] byStatPoint_03                 u8
  [  23] byStatPoint_04                 u8
  [  24] byStatPoint_05                 u8
  [  25] byStatPoint_06                 u8
  [  26] byStatPoint_07                 u8
  [  27] byStatPoint_08                 u8
  [  28] byStatPoint_09                 u8
  [  29] byStatPoint_10                 u8
  [  30] byStatPoint_11                 u8
  [  31] byStatPoint_12                 u8
  [  32] byStatPoint_13                 u8
  [  33] byStatPoint_14                 u8
  [  34] byStatPoint_15                 u8
  [  35] byStatPoint_16                 u8
  [  36] byStatPoint_17                 u8
  [  37] byStatPoint_18                 u8
  [  38] byStatPoint_19                 u8
  [  39] byStatPoint_20                 u8
  [  40] byStatPoint_21                 u8
  [  41] byStatPoint_22                 u8
  [  42] byStatPoint_23                 u8
  [  43] byStatPoint_24                 u8
  [  44] byStatPoint_25                 u8
  [  45] byStatPoint_26                 u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityStats {
        uint8_t byStatType;
        uint8_t byAction;
        uint16_t wMinPhyAtk;
        uint32_t dwMaxPhyAtk;
        uint16_t wMinMagAtk;
        uint64_t ullHP;
        uint8_t byStr;
        uint8_t byInt;
        uint8_t byStatPoint_01;
        uint8_t byStatPoint_02;
        uint8_t byStatPoint_03;
        uint8_t byStatPoint_04;
        uint8_t byStatPoint_05;
        uint8_t byStatPoint_06;
        uint8_t byStatPoint_07;
        uint8_t byStatPoint_08;
        uint8_t byStatPoint_09;
        uint8_t byStatPoint_10;
        uint8_t byStatPoint_11;
        uint8_t byStatPoint_12;
        uint8_t byStatPoint_13;
        uint8_t byStatPoint_14;
        uint8_t byStatPoint_15;
        uint8_t byStatPoint_16;
        uint8_t byStatPoint_17;
        uint8_t byStatPoint_18;
        uint8_t byStatPoint_19;
        uint8_t byStatPoint_20;
        uint8_t byStatPoint_21;
        uint8_t byStatPoint_22;
        uint8_t byStatPoint_23;
        uint8_t byStatPoint_24;
        uint8_t byStatPoint_25;
        uint16_t byStatPoint_26;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStats(
        byte byStatType,
        byte byAction,
        ushort wMinPhyAtk,
        uint dwMaxPhyAtk,
        ushort wMinMagAtk,
        ulong ullHP,
        byte byStr,
        byte byInt,
        byte byStatPoint_01,
        byte byStatPoint_02,
        byte byStatPoint_03,
        byte byStatPoint_04,
        byte byStatPoint_05,
        byte byStatPoint_06,
        byte byStatPoint_07,
        byte byStatPoint_08,
        byte byStatPoint_09,
        byte byStatPoint_10,
        byte byStatPoint_11,
        byte byStatPoint_12,
        byte byStatPoint_13,
        byte byStatPoint_14,
        byte byStatPoint_15,
        byte byStatPoint_16,
        byte byStatPoint_17,
        byte byStatPoint_18,
        byte byStatPoint_19,
        byte byStatPoint_20,
        byte byStatPoint_21,
        byte byStatPoint_22,
        byte byStatPoint_23,
        byte byStatPoint_24,
        byte byStatPoint_25,
        ushort byStatPoint_26
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStats {
        pub by_stat_type: u8,
        pub by_action: u8,
        pub w_min_phy_atk: u16,
        pub dw_max_phy_atk: u32,
        pub w_min_mag_atk: u16,
        pub ull_hp: u64,
        pub by_str: u8,
        pub by_int: u8,
        pub by_stat_point_01: u8,
        pub by_stat_point_02: u8,
        pub by_stat_point_03: u8,
        pub by_stat_point_04: u8,
        pub by_stat_point_05: u8,
        pub by_stat_point_06: u8,
        pub by_stat_point_07: u8,
        pub by_stat_point_08: u8,
        pub by_stat_point_09: u8,
        pub by_stat_point_10: u8,
        pub by_stat_point_11: u8,
        pub by_stat_point_12: u8,
        pub by_stat_point_13: u8,
        pub by_stat_point_14: u8,
        pub by_stat_point_15: u8,
        pub by_stat_point_16: u8,
        pub by_stat_point_17: u8,
        pub by_stat_point_18: u8,
        pub by_stat_point_19: u8,
        pub by_stat_point_20: u8,
        pub by_stat_point_21: u8,
        pub by_stat_point_22: u8,
        pub by_stat_point_23: u8,
        pub by_stat_point_24: u8,
        pub by_stat_point_25: u8,
        pub by_stat_point_26: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStats struct {
        byStatType uint8
        byAction uint8
        wMinPhyAtk uint16
        dwMaxPhyAtk uint32
        wMinMagAtk uint16
        ullHP uint64
        byStr uint8
        byInt uint8
        byStatPoint_01 uint8
        byStatPoint_02 uint8
        byStatPoint_03 uint8
        byStatPoint_04 uint8
        byStatPoint_05 uint8
        byStatPoint_06 uint8
        byStatPoint_07 uint8
        byStatPoint_08 uint8
        byStatPoint_09 uint8
        byStatPoint_10 uint8
        byStatPoint_11 uint8
        byStatPoint_12 uint8
        byStatPoint_13 uint8
        byStatPoint_14 uint8
        byStatPoint_15 uint8
        byStatPoint_16 uint8
        byStatPoint_17 uint8
        byStatPoint_18 uint8
        byStatPoint_19 uint8
        byStatPoint_20 uint8
        byStatPoint_21 uint8
        byStatPoint_22 uint8
        byStatPoint_23 uint8
        byStatPoint_24 uint8
        byStatPoint_25 uint8
        byStatPoint_26 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStats {
        byStatType: number;
        byAction: number;
        wMinPhyAtk: number;
        dwMaxPhyAtk: number;
        wMinMagAtk: number;
        ullHP: bigint;
        byStr: number;
        byInt: number;
        byStatPoint_01: number;
        byStatPoint_02: number;
        byStatPoint_03: number;
        byStatPoint_04: number;
        byStatPoint_05: number;
        byStatPoint_06: number;
        byStatPoint_07: number;
        byStatPoint_08: number;
        byStatPoint_09: number;
        byStatPoint_10: number;
        byStatPoint_11: number;
        byStatPoint_12: number;
        byStatPoint_13: number;
        byStatPoint_14: number;
        byStatPoint_15: number;
        byStatPoint_16: number;
        byStatPoint_17: number;
        byStatPoint_18: number;
        byStatPoint_19: number;
        byStatPoint_20: number;
        byStatPoint_21: number;
        byStatPoint_22: number;
        byStatPoint_23: number;
        byStatPoint_24: number;
        byStatPoint_25: number;
        byStatPoint_26: number;
    }
    ```

