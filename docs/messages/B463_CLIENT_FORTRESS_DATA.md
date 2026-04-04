# CLIENT_FORTRESS_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB463` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DCA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DCB0` |

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
    struct FortressData {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressData(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressData {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressData struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressData {
        byResult: number;
    }
    ```

