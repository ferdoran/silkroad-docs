# CLIENT_ACADEMY_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB11A` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00899060` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x00899081` |
| 2 | `dwField_02` | `u32` | 4 | `0x0089908F` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] dwField_02                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyData {
        uint32_t dwUniqueID;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyData(
        uint dwUniqueID,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyData {
        pub dw_unique_id: u32,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyData struct {
        dwUniqueID uint32
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyData {
        dwUniqueID: number;
        dwField_02: number;
    }
    ```

