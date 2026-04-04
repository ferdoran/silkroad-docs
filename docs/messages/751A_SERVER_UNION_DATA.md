# SERVER_UNION_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x751A` |
| Direction | Client → Server |
| Group | Guild Extended |
| Handler(s) | `0x0089A590` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A5A1` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A5D0` |
| 3 | `dwField_03` | `u32` | 4 | `0x0089A620` |
| 4 | `byField_04` | `u8` | 1 | `0x0089A62E` |
| 5 | `byField_05` | `u8` | 1 | `0x0089A63C` |
| 6 | `wField_06` | `u16` | 2 | `0x0089A64A` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] byField_05                     u8
  [   8] wField_06                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct UnionData {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint8_t byField_05;
        uint16_t wField_06;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record UnionData(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        byte byField_04,
        byte byField_05,
        ushort wField_06
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct UnionData {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub by_field_05: u8,
        pub w_field_06: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type UnionData struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        byField_04 uint8
        byField_05 uint8
        wField_06 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface UnionData {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        byField_04: number;
        byField_05: number;
        wField_06: number;
    }
    ```

