# SERVER_JOB_ALIAS
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3156` |
| Direction | Server → Client |
| Group | Game Extended |
| Handler(s) | `0x00872810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00872820` |
| 2 | `byField_02` | `u8` | 1 | `0x0087284F` |
| 3 | `byField_03` | `u8` | 1 | `0x00872865` |
| 4 | `dwField_04` | `u32` | 4 | `0x00872873` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] dwField_04                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct JobAlias {
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint32_t dwField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record JobAlias(
        byte byResult,
        byte byField_02,
        byte byField_03,
        uint dwField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct JobAlias {
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub dw_field_04: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type JobAlias struct {
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        dwField_04 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface JobAlias {
        byResult: number;
        byField_02: number;
        byField_03: number;
        dwField_04: number;
    }
    ```

