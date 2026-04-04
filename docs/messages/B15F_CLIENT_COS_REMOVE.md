# CLIENT_COS_REMOVE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB15F` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00899420` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0089943B` |
| 2 | `dwField_02` | `u32` | 4 | `0x00899449` |

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
    struct CosRemove {
        uint32_t dwUniqueID;
        uint32_t dwField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosRemove(
        uint dwUniqueID,
        uint dwField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosRemove {
        pub dw_unique_id: u32,
        pub dw_field_02: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosRemove struct {
        dwUniqueID uint32
        dwField_02 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosRemove {
        dwUniqueID: number;
        dwField_02: number;
    }
    ```

