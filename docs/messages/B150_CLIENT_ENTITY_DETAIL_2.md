# CLIENT_ENTITY_DETAIL_2
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB150` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00872940` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087294F` |

**Total size**: 1 bytes

### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityDetail2 {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityDetail2(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityDetail2 {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityDetail2 struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityDetail2 {
        byResult: number;
    }
    ```

