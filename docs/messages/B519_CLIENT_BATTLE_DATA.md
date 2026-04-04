# CLIENT_BATTLE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB519` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089DBF0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `bytesData` | `bytes` | variable | `0x0089DC4A` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089DD0B` |
| 3 | `bytesData_2` | `bytes` | variable | `0x0089DD18` |
| 4 | `wField_04` | `u16` | 2 | `0x004F7A7D` |
| 5 | `bytesData_4` | `bytes` | variable | `0x004F7AB9` |
| 6 | `bytesData_5` | `bytes` | variable | `0x0089DD64` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089DD7A` |
| 8 | `dwField_08` | `u32` | 4 | `0x0089DDB4` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089DDC2` |
| 10 | `dwField_10` | `u32` | 4 | `0x0089DDEA` |
| 11 | `bytesData_10` | `bytes` | variable | `0x0089DDF7` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089DE22` |
| 13 | `dwField_13` | `u32` | 4 | `0x0089DFA5` |

**Minimum size**: 30 bytes + variable fields

### Structure Summary

```
  [   0] bytesData                      bytes  (variable length)
  [   0] dwField_02                     u32
  [   4] bytesData_2                    bytes  (variable length)
  [   0] wField_04                      u16
  [   2] bytesData_4                    bytes  (variable length)
  [   0] bytesData_5                    bytes  (variable length)
  [   0] dwField_07                     u32
  [   4] dwField_08                     u32
  [   8] dwField_09                     u32
  [  12] dwField_10                     u32
  [  16] bytesData_10                   bytes  (variable length)
  [   0] dwField_12                     u32
  [   4] dwField_13                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleData {
        std::vector<uint8_t> bytesData;
        uint32_t dwField_02;
        std::vector<uint8_t> bytesData_2;
        uint16_t wField_04;
        std::vector<uint8_t> bytesData_4;
        std::vector<uint8_t> bytesData_5;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint32_t dwField_10;
        std::vector<uint8_t> bytesData_10;
        uint32_t dwField_12;
        uint32_t dwField_13;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleData(
        byte[] bytesData,
        uint dwField_02,
        byte[] bytesData_2,
        ushort wField_04,
        byte[] bytesData_4,
        byte[] bytesData_5,
        uint dwField_07,
        uint dwField_08,
        uint dwField_09,
        uint dwField_10,
        byte[] bytesData_10,
        uint dwField_12,
        uint dwField_13
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleData {
        pub bytes_data: Vec<u8>,
        pub dw_field_02: u32,
        pub bytes_data_2: Vec<u8>,
        pub w_field_04: u16,
        pub bytes_data_4: Vec<u8>,
        pub bytes_data_5: Vec<u8>,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub dw_field_10: u32,
        pub bytes_data_10: Vec<u8>,
        pub dw_field_12: u32,
        pub dw_field_13: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleData struct {
        bytesData []byte
        dwField_02 uint32
        bytesData_2 []byte
        wField_04 uint16
        bytesData_4 []byte
        bytesData_5 []byte
        dwField_07 uint32
        dwField_08 uint32
        dwField_09 uint32
        dwField_10 uint32
        bytesData_10 []byte
        dwField_12 uint32
        dwField_13 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleData {
        bytesData: Uint8Array;
        dwField_02: number;
        bytesData_2: Uint8Array;
        wField_04: number;
        bytesData_4: Uint8Array;
        bytesData_5: Uint8Array;
        dwField_07: number;
        dwField_08: number;
        dwField_09: number;
        dwField_10: number;
        bytesData_10: Uint8Array;
        dwField_12: number;
        dwField_13: number;
    }
    ```

