# CLIENT_WORLD_SPAWN_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB06D` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00884660` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwPartyID` | `u32` | 4 | `0x008846CC` |
| 2 | `dwLeaderID` | `u32` | 4 | `0x008846DA` |
| 3 | `dwParam1` | `u32` | 4 | `0x008846E8` |
| 4 | `dwParam2` | `u32` | 4 | `0x008846F6` |
| 5 | `dwParam3` | `u32` | 4 | `0x00884704` |
| 6 | `byJoinFlag` | `u8` | 1 | `0x00884712` |
| 7 | `byField_07` | `u8` | 1 | `0x00883638` |
| 8 | `dwField_08` | `u32` | 4 | `0x0088364B` |
| 9 | `wField_09` | `u16` | 2 | `0x0087356D` |
| 10 | `bytesData_9` | `bytes` | variable | `0x008735A9` |
| 11 | `dwField_11` | `u32` | 4 | `0x00883668` |
| 12 | `byField_12` | `u8` | 1 | `0x0088367A` |
| 13 | `byField_13` | `u8` | 1 | `0x0088368C` |
| 14 | `wField_14` | `u16` | 2 | `0x008836A4` |
| 15 | `dwField_15` | `u32` | 4 | `0x008836B9` |
| 16 | `dwField_16` | `u32` | 4 | `0x008836C6` |
| 17 | `dwField_17` | `u32` | 4 | `0x008836D3` |
| 18 | `wField_18` | `u16` | 2 | `0x008836F9` |
| 19 | `wField_19` | `u16` | 2 | `0x00883703` |
| 20 | `wField_20` | `u16` | 2 | `0x0088370D` |
| 21 | `dwField_21` | `u32` | 4 | `0x00883726` |
| 22 | `byField_22` | `u8` | 1 | `0x00883747` |
| 23 | `dwField_23` | `u32` | 4 | `0x00883759` |
| 24 | `dwField_24` | `u32` | 4 | `0x00883766` |

**Minimum size**: 67 bytes + variable fields

### Structure Summary

```
  [   0] dwPartyID                      u32
  [   4] dwLeaderID                     u32
  [   8] dwParam1                       u32
  [  12] dwParam2                       u32
  [  16] dwParam3                       u32
  [  20] byJoinFlag                     u8
  [  21] byField_07                     u8
  [  22] dwField_08                     u32
  [  26] wField_09                      u16
  [  28] bytesData_9                    bytes  (variable length)
  [   0] dwField_11                     u32
  [   4] byField_12                     u8
  [   5] byField_13                     u8
  [   6] wField_14                      u16
  [   8] dwField_15                     u32
  [  12] dwField_16                     u32
  [  16] dwField_17                     u32
  [  20] wField_18                      u16
  [  22] wField_19                      u16
  [  24] wField_20                      u16
  [  26] dwField_21                     u32
  [  30] byField_22                     u8
  [  31] dwField_23                     u32
  [  35] dwField_24                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct WorldSpawnRequest {
        uint32_t dwPartyID;
        uint32_t dwLeaderID;
        uint32_t dwParam1;
        uint32_t dwParam2;
        uint32_t dwParam3;
        uint8_t byJoinFlag;
        uint8_t byField_07;
        uint32_t dwField_08;
        uint16_t wField_09;
        std::vector<uint8_t> bytesData_9;
        uint32_t dwField_11;
        uint8_t byField_12;
        uint8_t byField_13;
        uint16_t wField_14;
        uint32_t dwField_15;
        uint32_t dwField_16;
        uint32_t dwField_17;
        uint16_t wField_18;
        uint16_t wField_19;
        uint16_t wField_20;
        uint32_t dwField_21;
        uint8_t byField_22;
        uint32_t dwField_23;
        uint32_t dwField_24;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record WorldSpawnRequest(
        uint dwPartyID,
        uint dwLeaderID,
        uint dwParam1,
        uint dwParam2,
        uint dwParam3,
        byte byJoinFlag,
        byte byField_07,
        uint dwField_08,
        ushort wField_09,
        byte[] bytesData_9,
        uint dwField_11,
        byte byField_12,
        byte byField_13,
        ushort wField_14,
        uint dwField_15,
        uint dwField_16,
        uint dwField_17,
        ushort wField_18,
        ushort wField_19,
        ushort wField_20,
        uint dwField_21,
        byte byField_22,
        uint dwField_23,
        uint dwField_24
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct WorldSpawnRequest {
        pub dw_party_id: u32,
        pub dw_leader_id: u32,
        pub dw_param1: u32,
        pub dw_param2: u32,
        pub dw_param3: u32,
        pub by_join_flag: u8,
        pub by_field_07: u8,
        pub dw_field_08: u32,
        pub w_field_09: u16,
        pub bytes_data_9: Vec<u8>,
        pub dw_field_11: u32,
        pub by_field_12: u8,
        pub by_field_13: u8,
        pub w_field_14: u16,
        pub dw_field_15: u32,
        pub dw_field_16: u32,
        pub dw_field_17: u32,
        pub w_field_18: u16,
        pub w_field_19: u16,
        pub w_field_20: u16,
        pub dw_field_21: u32,
        pub by_field_22: u8,
        pub dw_field_23: u32,
        pub dw_field_24: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type WorldSpawnRequest struct {
        dwPartyID uint32
        dwLeaderID uint32
        dwParam1 uint32
        dwParam2 uint32
        dwParam3 uint32
        byJoinFlag uint8
        byField_07 uint8
        dwField_08 uint32
        wField_09 uint16
        bytesData_9 []byte
        dwField_11 uint32
        byField_12 uint8
        byField_13 uint8
        wField_14 uint16
        dwField_15 uint32
        dwField_16 uint32
        dwField_17 uint32
        wField_18 uint16
        wField_19 uint16
        wField_20 uint16
        dwField_21 uint32
        byField_22 uint8
        dwField_23 uint32
        dwField_24 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface WorldSpawnRequest {
        dwPartyID: number;
        dwLeaderID: number;
        dwParam1: number;
        dwParam2: number;
        dwParam3: number;
        byJoinFlag: number;
        byField_07: number;
        dwField_08: number;
        wField_09: number;
        bytesData_9: Uint8Array;
        dwField_11: number;
        byField_12: number;
        byField_13: number;
        wField_14: number;
        dwField_15: number;
        dwField_16: number;
        dwField_17: number;
        wField_18: number;
        wField_19: number;
        wField_20: number;
        dwField_21: number;
        byField_22: number;
        dwField_23: number;
        dwField_24: number;
    }
    ```

