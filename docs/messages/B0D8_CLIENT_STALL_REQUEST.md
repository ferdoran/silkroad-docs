# CLIENT_STALL_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0D8` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008812B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008812E3` |
| 2 | `dwParam` | `u32` | 4 | `0x008812F1` |
| 3 | `byField_03` | `u8` | 1 | `0x008B94E5` |
| 4 | `byField_04` | `u8` | 1 | `0x008B94F2` |
| 5 | `byField_05` | `u8` | 1 | `0x008B94FF` |
| 6 | `dwField_06` | `u32` | 4 | `0x008B9511` |
| 7 | `byField_07` | `u8` | 1 | `0x008B954E` |
| 8 | `byField_08` | `u8` | 1 | `0x008B9560` |
| 9 | `byField_09` | `u8` | 1 | `0x008B9579` |
| 10 | `byField_10` | `u8` | 1 | `0x008B6F3D` |
| 11 | `byField_11` | `u8` | 1 | `0x008B6F56` |
| 12 | `dwField_12` | `u32` | 4 | `0x008B6FFF` |
| 13 | `byField_13` | `u8` | 1 | `0x008B95EA` |
| 14 | `dwField_14` | `u32` | 4 | `0x008B9609` |

**Total size**: 26 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwParam                        u32
  [   5] byField_03                     u8
  [   6] byField_04                     u8
  [   7] byField_05                     u8
  [   8] dwField_06                     u32
  [  12] byField_07                     u8
  [  13] byField_08                     u8
  [  14] byField_09                     u8
  [  15] byField_10                     u8
  [  16] byField_11                     u8
  [  17] dwField_12                     u32
  [  21] byField_13                     u8
  [  22] dwField_14                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallRequest {
        uint8_t byAction;
        uint32_t dwParam;
        uint8_t byField_03;
        uint8_t byField_04;
        uint8_t byField_05;
        uint32_t dwField_06;
        uint8_t byField_07;
        uint8_t byField_08;
        uint8_t byField_09;
        uint8_t byField_10;
        uint8_t byField_11;
        uint32_t dwField_12;
        uint8_t byField_13;
        uint32_t dwField_14;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallRequest(
        byte byAction,
        uint dwParam,
        byte byField_03,
        byte byField_04,
        byte byField_05,
        uint dwField_06,
        byte byField_07,
        byte byField_08,
        byte byField_09,
        byte byField_10,
        byte byField_11,
        uint dwField_12,
        byte byField_13,
        uint dwField_14
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallRequest {
        pub by_action: u8,
        pub dw_param: u32,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub by_field_05: u8,
        pub dw_field_06: u32,
        pub by_field_07: u8,
        pub by_field_08: u8,
        pub by_field_09: u8,
        pub by_field_10: u8,
        pub by_field_11: u8,
        pub dw_field_12: u32,
        pub by_field_13: u8,
        pub dw_field_14: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallRequest struct {
        byAction uint8
        dwParam uint32
        byField_03 uint8
        byField_04 uint8
        byField_05 uint8
        dwField_06 uint32
        byField_07 uint8
        byField_08 uint8
        byField_09 uint8
        byField_10 uint8
        byField_11 uint8
        dwField_12 uint32
        byField_13 uint8
        dwField_14 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallRequest {
        byAction: number;
        dwParam: number;
        byField_03: number;
        byField_04: number;
        byField_05: number;
        dwField_06: number;
        byField_07: number;
        byField_08: number;
        byField_09: number;
        byField_10: number;
        byField_11: number;
        dwField_12: number;
        byField_13: number;
        dwField_14: number;
    }
    ```

