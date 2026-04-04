# SERVER_FORTRESS_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x34D5` |
| Direction | Server → Client |
| Group | Game Extended 4 |
| Handler(s) | `0x0088E210` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `wParam` | `u16` | 2 | `0x0088E21F` |
| 2 | `dwField_02` | `u32` | 4 | `0x0088E249` |
| 3 | `wField_03` | `u16` | 2 | `0x0088E257` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] wParam                         u16
  [   2] dwField_02                     u32
  [   6] wField_03                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct FortressInfo {
        uint16_t wParam;
        uint32_t dwField_02;
        uint16_t wField_03;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressInfo(
        ushort wParam,
        uint dwField_02,
        ushort wField_03
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressInfo {
        pub w_param: u16,
        pub dw_field_02: u32,
        pub w_field_03: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressInfo struct {
        wParam uint16
        dwField_02 uint32
        wField_03 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressInfo {
        wParam: number;
        dwField_02: number;
        wField_03: number;
    }
    ```

