# CLIENT_NPC_DATA_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0C6` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A6650` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byRequestType` | `u32` | 4 | `0x009A19AA` |
| 2 | `dwField_02` | `u32` | 4 | `0x009A19B8` |
| 3 | `dwField_03` | `u32` | 4 | `0x009A1AB6` |
| 4 | `dwField_04` | `u32` | 4 | `0x009A1AC4` |
| 5 | `ullField_05` | `u64` | 8 | `0x009A1ADA` |
| 6 | `byField_06` | `u8` | 1 | `0x009A1AE8` |
| 7 | `wField_07` | `u16` | 2 | `0x009A1AF6` |
| 8 | `dwField_08` | `u32` | 4 | `0x009A1B69` |
| 9 | `byField_09` | `u8` | 1 | `0x009A1BB2` |
| 10 | `byField_10` | `u8` | 1 | `0x009A1CB3` |
| 11 | `byField_11` | `u8` | 1 | `0x009A1CCE` |
| 12 | `dwField_12` | `u32` | 4 | `0x009A1D12` |
| 13 | `byField_13` | `u8` | 1 | `0x009A1D41` |

**Total size**: 39 bytes

### Structure Summary

```
  [   0] byRequestType                  u32
  [   4] dwField_02                     u32
  [   8] dwField_03                     u32
  [  12] dwField_04                     u32
  [  16] ullField_05                    u64
  [  24] byField_06                     u8
  [  25] wField_07                      u16
  [  27] dwField_08                     u32
  [  31] byField_09                     u8
  [  32] byField_10                     u8
  [  33] byField_11                     u8
  [  34] dwField_12                     u32
  [  38] byField_13                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct NpcDataRequest {
        uint32_t byRequestType;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint32_t dwField_04;
        uint64_t ullField_05;
        uint8_t byField_06;
        uint16_t wField_07;
        uint32_t dwField_08;
        uint8_t byField_09;
        uint8_t byField_10;
        uint8_t byField_11;
        uint32_t dwField_12;
        uint8_t byField_13;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record NpcDataRequest(
        uint byRequestType,
        uint dwField_02,
        uint dwField_03,
        uint dwField_04,
        ulong ullField_05,
        byte byField_06,
        ushort wField_07,
        uint dwField_08,
        byte byField_09,
        byte byField_10,
        byte byField_11,
        uint dwField_12,
        byte byField_13
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct NpcDataRequest {
        pub by_request_type: u32,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub dw_field_04: u32,
        pub ull_field_05: u64,
        pub by_field_06: u8,
        pub w_field_07: u16,
        pub dw_field_08: u32,
        pub by_field_09: u8,
        pub by_field_10: u8,
        pub by_field_11: u8,
        pub dw_field_12: u32,
        pub by_field_13: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type NpcDataRequest struct {
        byRequestType uint32
        dwField_02 uint32
        dwField_03 uint32
        dwField_04 uint32
        ullField_05 uint64
        byField_06 uint8
        wField_07 uint16
        dwField_08 uint32
        byField_09 uint8
        byField_10 uint8
        byField_11 uint8
        dwField_12 uint32
        byField_13 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface NpcDataRequest {
        byRequestType: number;
        dwField_02: number;
        dwField_03: number;
        dwField_04: number;
        ullField_05: bigint;
        byField_06: number;
        wField_07: number;
        dwField_08: number;
        byField_09: number;
        byField_10: number;
        byField_11: number;
        dwField_12: number;
        byField_13: number;
    }
    ```

