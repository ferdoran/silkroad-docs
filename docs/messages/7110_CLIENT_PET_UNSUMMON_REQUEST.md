# CLIENT_PET_UNSUMMON_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

> **Corrected name** (server RE): Was `SERVER_FRIEND_DATA` (client-derived). Direction: Client→Server (0x7xxx). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x7110` |
| Direction | Client → Server |
| Group | Chat Extended |
| Handler(s) | `0x0087FD90` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0099AB67` |
| 2 | `dwField_02` | `u32` | 4 | `0x0087FF1D` |
| 3 | `dwField_03` | `u32` | 4 | `0x0087FF2F` |
| 4 | `byField_04` | `u8` | 1 | `0x0087FF3C` |
| 5 | `dwField_05` | `u32` | 4 | `0x0087FF49` |
| 6 | `dwField_06` | `u32` | 4 | `0x0087FF56` |
| 7 | `dwField_07` | `u32` | 4 | `0x0087FF63` |
| 8 | `dwField_08` | `u32` | 4 | `0x0087FF70` |
| 9 | `dwField_09` | `u32` | 4 | `0x0087FF7D` |
| 10 | `wField_10` | `u16` | 2 | `0x004F7A7D` |
| 11 | `bytesData_10` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 32 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] dwField_05                     u32
  [  14] dwField_06                     u32
  [  18] dwField_07                     u32
  [  22] dwField_08                     u32
  [  26] dwField_09                     u32
  [  30] wField_10                      u16
  [  32] bytesData_10                   bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PetUnsummonRequest {
        uint8_t byResult;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint16_t wField_10;
        std::vector<uint8_t> bytesData_10;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PetUnsummonRequest(
        byte byResult,
        uint dwField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06,
        uint dwField_07,
        uint dwField_08,
        uint dwField_09,
        ushort wField_10,
        byte[] bytesData_10
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PetUnsummonRequest {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub w_field_10: u16,
        pub bytes_data_10: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type PetUnsummonRequest struct {
        byResult uint8
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
        dwField_07 uint32
        dwField_08 uint32
        dwField_09 uint32
        wField_10 uint16
        bytesData_10 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PetUnsummonRequest {
        byResult: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
        dwField_07: number;
        dwField_08: number;
        dwField_09: number;
        wField_10: number;
        bytesData_10: Uint8Array;
    }
    ```

