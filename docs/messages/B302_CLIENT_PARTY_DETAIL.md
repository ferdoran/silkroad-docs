# CLIENT_PARTY_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB302` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x0087FDD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x009993F1` |
| 2 | `dwField_02` | `u32` | 4 | `0x00999439` |
| 3 | `wField_03` | `u16` | 2 | `0x00999447` |
| 4 | `bytesData_3` | `bytes` | variable | `0x00999489` |
| 5 | `dwField_05` | `u32` | 4 | `0x00999497` |
| 6 | `byField_06` | `u8` | 1 | `0x009994A5` |

**Minimum size**: 12 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwField_02                     u32
  [   5] wField_03                      u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] byField_06                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyDetail {
        uint8_t byResult;
        uint32_t dwField_02;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
        uint32_t dwField_05;
        uint8_t byField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyDetail(
        byte byResult,
        uint dwField_02,
        ushort wField_03,
        byte[] bytesData_3,
        uint dwField_05,
        byte byField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyDetail {
        pub by_result: u8,
        pub dw_field_02: u32,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
        pub dw_field_05: u32,
        pub by_field_06: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyDetail struct {
        byResult uint8
        dwField_02 uint32
        wField_03 uint16
        bytesData_3 []byte
        dwField_05 uint32
        byField_06 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyDetail {
        byResult: number;
        dwField_02: number;
        wField_03: number;
        bytesData_3: Uint8Array;
        dwField_05: number;
        byField_06: number;
    }
    ```

