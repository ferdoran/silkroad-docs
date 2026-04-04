# SERVER_ENTITY_SELECTION

> **Corrected name** (server RE): Was `CLIENT_NPC_INTERACT` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB045` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A9E30` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `wFlags` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `unk` | `u32` | 4 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A9E6F` |
| 2 | `wFlags` | `u16` | 2 | `0x008A9E7D` |
| 3 | `byHasUpdate` | `u8` | 1 | `0x008A9EBF` |
| 4 | `dwParam1` | `u32` | 4 | `0x008A9ED6` |
| 5 | `dwParam2` | `u32` | 4 | `0x008A9EF0` |
| 6 | `wStatusFlags` | `u16` | 2 | `0x008A9F0A` |
| 7 | `byStateFlags` | `u8` | 1 | `0x008A9F5D` |
| 8 | `dwStateParam` | `u32` | 4 | `0x008A9F8F` |
| 9 | `dwAutoPotion` | `u32` | 4 | `0x008AA16B` |
| 10 | `wBuffFlags` | `u16` | 2 | `0x008AA1D1` |
| 11 | `dwAbnormalState` | `u32` | 4 | `0x008AA22C` |
| 12 | `dwField_12` | `u32` | 4 | `0x008AB134` |
| 13 | `dwField_13` | `u32` | 4 | `0x008AB249` |
| 14 | `dwField_14` | `u32` | 4 | `0x008AB2BF` |
| 15 | `byField_15` | `u8` | 1 | `0x008AB2D9` |
| 16 | `dwField_16` | `u32` | 4 | `0x008AB309` |
| 17 | `byField_17` | `u8` | 1 | `0x009D2326` |

**Total size**: 50 bytes

</details>
### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] wFlags                         u16
  [   6] byHasUpdate                    u8
  [   7] dwParam1                       u32
  [  11] dwParam2                       u32
  [  15] wStatusFlags                   u16
  [  17] byStateFlags                   u8
  [  18] dwStateParam                   u32
  [  22] dwAutoPotion                   u32
  [  26] wBuffFlags                     u16
  [  28] dwAbnormalState                u32
  [  32] dwField_12                     u32
  [  36] dwField_13                     u32
  [  40] dwField_14                     u32
  [  44] byField_15                     u8
  [  45] dwField_16                     u32
  [  49] byField_17                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySelection {
        uint32_t dwUniqueID;
        uint16_t wFlags;
        uint8_t byHasUpdate;
        uint32_t dwParam1;
        uint32_t dwParam2;
        uint16_t wStatusFlags;
        uint8_t byStateFlags;
        uint32_t dwStateParam;
        uint32_t dwAutoPotion;
        uint16_t wBuffFlags;
        uint32_t dwAbnormalState;
        uint32_t dwField_12;
        uint32_t dwField_13;
        uint32_t dwField_14;
        uint8_t byField_15;
        uint32_t dwField_16;
        uint8_t byField_17;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySelection(
        uint dwUniqueID,
        ushort wFlags,
        byte byHasUpdate,
        uint dwParam1,
        uint dwParam2,
        ushort wStatusFlags,
        byte byStateFlags,
        uint dwStateParam,
        uint dwAutoPotion,
        ushort wBuffFlags,
        uint dwAbnormalState,
        uint dwField_12,
        uint dwField_13,
        uint dwField_14,
        byte byField_15,
        uint dwField_16,
        byte byField_17
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySelection {
        pub dw_unique_id: u32,
        pub w_flags: u16,
        pub by_has_update: u8,
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub w_status_flags: u16,
        pub by_state_flags: u8,
        pub dw_state_param: u32,
        pub dw_auto_potion: u32,
        pub w_buff_flags: u16,
        pub dw_abnormal_state: u32,
        pub dw_field_12: u32,
        pub dw_field_13: u32,
        pub dw_field_14: u32,
        pub by_field_15: u8,
        pub dw_field_16: u32,
        pub by_field_17: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySelection struct {
        dwUniqueID uint32
        wFlags uint16
        byHasUpdate uint8
        dwParam1 uint32
        dwParam2 uint32
        wStatusFlags uint16
        byStateFlags uint8
        dwStateParam uint32
        dwAutoPotion uint32
        wBuffFlags uint16
        dwAbnormalState uint32
        dwField_12 uint32
        dwField_13 uint32
        dwField_14 uint32
        byField_15 uint8
        dwField_16 uint32
        byField_17 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySelection {
        dwUniqueID: number;
        wFlags: number;
        byHasUpdate: number;
        dwParam1: number;
        dwParam2: number;
        wStatusFlags: number;
        byStateFlags: number;
        dwStateParam: number;
        dwAutoPotion: number;
        wBuffFlags: number;
        dwAbnormalState: number;
        dwField_12: number;
        dwField_13: number;
        dwField_14: number;
        byField_15: number;
        dwField_16: number;
        byField_17: number;
    }
    ```

