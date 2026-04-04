# CLIENT_ENTITY_EQUIPMENT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0E5` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088A130` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088A16F` |
| 2 | `byJobRankType` | `u8` | 1 | `0x0088A189` |
| 3 | `byJobLevel` | `u8` | 1 | `0x0088A197` |
| 4 | `byHasData` | `u8` | 1 | `0x0088A1A5` |
| 5 | `byCount1` | `u8` | 1 | `0x0088A210` |
| 6 | `bySlot1` | `u16` | 2 | `0x0087356D` |
| 7 | `dwRefItemID1` | `bytes` | variable | `0x008735A9` |
| 8 | `byOptLevel1` | `u8` | 1 | `0x0088A22C` |
| 9 | `byCount2` | `u32` | 4 | `0x0088A23A` |
| 10 | `bySlot2` | `u8` | 1 | `0x0088A248` |
| 11 | `dwRefItemID2` | `u8` | 1 | `0x0088A316` |
| 12 | `byOptLevel2` | `u8` | 1 | `0x0088A332` |
| 13 | `wExtraParam` | `u32` | 4 | `0x0088A340` |
| 14 | `byExtra1` | `u16` | 2 | `0x0088A3BA` |
| 15 | `byExtra2` | `u8` | 1 | `0x0088A3C8` |
| 16 | `byField_16` | `u8` | 1 | `0x0088A3D6` |

**Minimum size**: 23 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byJobRankType                  u8
  [   2] byJobLevel                     u8
  [   3] byHasData                      u8
  [   4] byCount1                       u8
  [   5] bySlot1                        u16
  [   7] dwRefItemID1                   bytes  (variable length)
  [   0] byOptLevel1                    u8
  [   1] byCount2                       u32
  [   5] bySlot2                        u8
  [   6] dwRefItemID2                   u8
  [   7] byOptLevel2                    u8
  [   8] wExtraParam                    u32
  [  12] byExtra1                       u16
  [  14] byExtra2                       u8
  [  15] byField_16                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityEquipment {
        uint8_t byResult;
        uint8_t byJobRankType;
        uint8_t byJobLevel;
        uint8_t byHasData;
        uint8_t byCount1;
        uint16_t bySlot1;
        std::vector<uint8_t> dwRefItemID1;
        uint8_t byOptLevel1;
        uint32_t byCount2;
        uint8_t bySlot2;
        uint8_t dwRefItemID2;
        uint8_t byOptLevel2;
        uint32_t wExtraParam;
        uint16_t byExtra1;
        uint8_t byExtra2;
        uint8_t byField_16;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityEquipment(
        byte byResult,
        byte byJobRankType,
        byte byJobLevel,
        byte byHasData,
        byte byCount1,
        ushort bySlot1,
        byte[] dwRefItemID1,
        byte byOptLevel1,
        uint byCount2,
        byte bySlot2,
        byte dwRefItemID2,
        byte byOptLevel2,
        uint wExtraParam,
        ushort byExtra1,
        byte byExtra2,
        byte byField_16
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityEquipment {
        pub by_result: u8,
        pub by_job_rank_type: u8,
        pub by_job_level: u8,
        pub by_has_data: u8,
        pub by_count1: u8,
        pub by_slot1: u16,
        pub dw_ref_item_id1: Vec<u8>,
        pub by_opt_level1: u8,
        pub by_count2: u32,
        pub by_slot2: u8,
        pub dw_ref_item_id2: u8,
        pub by_opt_level2: u8,
        pub w_extra_param: u32,
        pub by_extra1: u16,
        pub by_extra2: u8,
        pub by_field_16: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityEquipment struct {
        byResult uint8
        byJobRankType uint8
        byJobLevel uint8
        byHasData uint8
        byCount1 uint8
        bySlot1 uint16
        dwRefItemID1 []byte
        byOptLevel1 uint8
        byCount2 uint32
        bySlot2 uint8
        dwRefItemID2 uint8
        byOptLevel2 uint8
        wExtraParam uint32
        byExtra1 uint16
        byExtra2 uint8
        byField_16 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityEquipment {
        byResult: number;
        byJobRankType: number;
        byJobLevel: number;
        byHasData: number;
        byCount1: number;
        bySlot1: number;
        dwRefItemID1: Uint8Array;
        byOptLevel1: number;
        byCount2: number;
        bySlot2: number;
        dwRefItemID2: number;
        byOptLevel2: number;
        wExtraParam: number;
        byExtra1: number;
        byExtra2: number;
        byField_16: number;
    }
    ```

