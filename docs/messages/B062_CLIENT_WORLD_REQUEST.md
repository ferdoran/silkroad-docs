# CLIENT_WORLD_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB062` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00883CC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byMemberCount` | `u8` | 1 | `0x00883D05` |
| 2 | `dwPartyID` | `u32` | 4 | `0x00883D28` |
| 3 | `dwLeaderID` | `u32` | 4 | `0x00883D50` |
| 4 | `byLevel` | `u8` | 1 | `0x00883D5E` |
| 5 | `byMemberType` | `u8` | 1 | `0x00883E2E` |
| 6 | `byField_06` | `u8` | 1 | `0x00883638` |
| 7 | `dwField_07` | `u32` | 4 | `0x0088364B` |
| 8 | `wField_08` | `u16` | 2 | `0x0087356D` |
| 9 | `bytesData_8` | `bytes` | variable | `0x008735A9` |
| 10 | `dwField_10` | `u32` | 4 | `0x00883668` |
| 11 | `byField_11` | `u8` | 1 | `0x0088367A` |
| 12 | `byField_12` | `u8` | 1 | `0x0088368C` |
| 13 | `wField_13` | `u16` | 2 | `0x008836A4` |
| 14 | `dwField_14` | `u32` | 4 | `0x008836B9` |
| 15 | `dwField_15` | `u32` | 4 | `0x008836C6` |
| 16 | `dwField_16` | `u32` | 4 | `0x008836D3` |
| 17 | `wField_17` | `u16` | 2 | `0x008836F9` |
| 18 | `wField_18` | `u16` | 2 | `0x00883703` |
| 19 | `wField_19` | `u16` | 2 | `0x0088370D` |
| 20 | `dwField_20` | `u32` | 4 | `0x00883726` |
| 21 | `byField_21` | `u8` | 1 | `0x00883747` |
| 22 | `dwField_22` | `u32` | 4 | `0x00883759` |
| 23 | `dwField_23` | `u32` | 4 | `0x00883766` |

**Minimum size**: 57 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `OnPartyInfo[%d]` | Debug |
| `Party  member name very short!!` | Debug |

### Structure Summary

```
  [   0] byMemberCount                  u8
  [   1] dwPartyID                      u32
  [   5] dwLeaderID                     u32
  [   9] byLevel                        u8
  [  10] byMemberType                   u8
  [  11] byField_06                     u8
  [  12] dwField_07                     u32
  [  16] wField_08                      u16
  [  18] bytesData_8                    bytes  (variable length)
  [   0] dwField_10                     u32
  [   4] byField_11                     u8
  [   5] byField_12                     u8
  [   6] wField_13                      u16
  [   8] dwField_14                     u32
  [  12] dwField_15                     u32
  [  16] dwField_16                     u32
  [  20] wField_17                      u16
  [  22] wField_18                      u16
  [  24] wField_19                      u16
  [  26] dwField_20                     u32
  [  30] byField_21                     u8
  [  31] dwField_22                     u32
  [  35] dwField_23                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct WorldRequest {
        uint8_t byMemberCount;
        uint32_t dwPartyID;
        uint32_t dwLeaderID;
        uint8_t byLevel;
        uint8_t byMemberType;
        uint8_t byField_06;
        uint32_t dwField_07;
        uint16_t wField_08;
        std::vector<uint8_t> bytesData_8;
        uint32_t dwField_10;
        uint8_t byField_11;
        uint8_t byField_12;
        uint16_t wField_13;
        uint32_t dwField_14;
        uint32_t dwField_15;
        uint32_t dwField_16;
        uint16_t wField_17;
        uint16_t wField_18;
        uint16_t wField_19;
        uint32_t dwField_20;
        uint8_t byField_21;
        uint32_t dwField_22;
        uint32_t dwField_23;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record WorldRequest(
        byte byMemberCount,
        uint dwPartyID,
        uint dwLeaderID,
        byte byLevel,
        byte byMemberType,
        byte byField_06,
        uint dwField_07,
        ushort wField_08,
        byte[] bytesData_8,
        uint dwField_10,
        byte byField_11,
        byte byField_12,
        ushort wField_13,
        uint dwField_14,
        uint dwField_15,
        uint dwField_16,
        ushort wField_17,
        ushort wField_18,
        ushort wField_19,
        uint dwField_20,
        byte byField_21,
        uint dwField_22,
        uint dwField_23
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct WorldRequest {
        pub by_member_count: u8,
        pub dw_party_id: u32,
        pub dw_leader_id: u32,
        pub by_level: u8,
        pub by_member_type: u8,
        pub by_field_06: u8,
        pub dw_field_07: u32,
        pub w_field_08: u16,
        pub bytes_data_8: Vec<u8>,
        pub dw_field_10: u32,
        pub by_field_11: u8,
        pub by_field_12: u8,
        pub w_field_13: u16,
        pub dw_field_14: u32,
        pub dw_field_15: u32,
        pub dw_field_16: u32,
        pub w_field_17: u16,
        pub w_field_18: u16,
        pub w_field_19: u16,
        pub dw_field_20: u32,
        pub by_field_21: u8,
        pub dw_field_22: u32,
        pub dw_field_23: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type WorldRequest struct {
        byMemberCount uint8
        dwPartyID uint32
        dwLeaderID uint32
        byLevel uint8
        byMemberType uint8
        byField_06 uint8
        dwField_07 uint32
        wField_08 uint16
        bytesData_8 []byte
        dwField_10 uint32
        byField_11 uint8
        byField_12 uint8
        wField_13 uint16
        dwField_14 uint32
        dwField_15 uint32
        dwField_16 uint32
        wField_17 uint16
        wField_18 uint16
        wField_19 uint16
        dwField_20 uint32
        byField_21 uint8
        dwField_22 uint32
        dwField_23 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface WorldRequest {
        byMemberCount: number;
        dwPartyID: number;
        dwLeaderID: number;
        byLevel: number;
        byMemberType: number;
        byField_06: number;
        dwField_07: number;
        wField_08: number;
        bytesData_8: Uint8Array;
        dwField_10: number;
        byField_11: number;
        byField_12: number;
        wField_13: number;
        dwField_14: number;
        dwField_15: number;
        dwField_16: number;
        wField_17: number;
        wField_18: number;
        wField_19: number;
        dwField_20: number;
        byField_21: number;
        dwField_22: number;
        dwField_23: number;
    }
    ```

