# SERVER_STALL_PURCHASE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3C87` |
| Direction | Server → Client |
| Group | Stall/Exchange |
| Handler(s) | `0x0089B7B0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089B80A` |
| 2 | `byField_02` | `u8` | 1 | `0x0089B834` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089B855` |
| 4 | `dwField_04` | `u32` | 4 | `0x0089B863` |
| 5 | `dwField_05` | `u32` | 4 | `0x0089B871` |
| 6 | `byField_06` | `u8` | 1 | `0x0089B92E` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089B94B` |
| 8 | `dwField_08` | `u32` | 4 | `0x0089B959` |
| 9 | `dwField_09` | `u32` | 4 | `0x0089B967` |
| 10 | `byField_10` | `u8` | 1 | `0x0089B9F8` |
| 11 | `dwField_11` | `u32` | 4 | `0x0089BA11` |
| 12 | `dwField_12` | `u32` | 4 | `0x0089BA1F` |
| 13 | `dwField_13` | `u32` | 4 | `0x0089BA2D` |

**Total size**: 40 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_TC_RECIEVE_BUFF` | UI |
| `UIIT_MSG_TC_PASS_ERROR` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] dwField_04                     u32
  [  10] dwField_05                     u32
  [  14] byField_06                     u8
  [  15] dwField_07                     u32
  [  19] dwField_08                     u32
  [  23] dwField_09                     u32
  [  27] byField_10                     u8
  [  28] dwField_11                     u32
  [  32] dwField_12                     u32
  [  36] dwField_13                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallPurchase {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint32_t dwField_04;
        uint32_t dwField_05;
        uint8_t byField_06;
        uint32_t dwField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint8_t byField_10;
        uint32_t dwField_11;
        uint32_t dwField_12;
        uint32_t dwField_13;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallPurchase(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        uint dwField_04,
        uint dwField_05,
        byte byField_06,
        uint dwField_07,
        uint dwField_08,
        uint dwField_09,
        byte byField_10,
        uint dwField_11,
        uint dwField_12,
        uint dwField_13
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallPurchase {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub dw_field_04: u32,
        pub dw_field_05: u32,
        pub by_field_06: u8,
        pub dw_field_07: u32,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub by_field_10: u8,
        pub dw_field_11: u32,
        pub dw_field_12: u32,
        pub dw_field_13: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallPurchase struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        dwField_04 uint32
        dwField_05 uint32
        byField_06 uint8
        dwField_07 uint32
        dwField_08 uint32
        dwField_09 uint32
        byField_10 uint8
        dwField_11 uint32
        dwField_12 uint32
        dwField_13 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallPurchase {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        dwField_04: number;
        dwField_05: number;
        byField_06: number;
        dwField_07: number;
        dwField_08: number;
        dwField_09: number;
        byField_10: number;
        dwField_11: number;
        dwField_12: number;
        dwField_13: number;
    }
    ```

