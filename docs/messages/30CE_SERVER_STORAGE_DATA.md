# SERVER_STORAGE_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30CE` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00881090` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwGold` | `u32` | 4 | `0x0088109C` |

**Total size**: 4 bytes

### String References
| String | Type |
|--------|------|
| `(Test_GM)PK Penalties:%dseconds` | Debug |

### Structure Summary

```
  [   0] dwGold                         u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StorageData {
        uint32_t dwGold;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StorageData(
        uint dwGold
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StorageData {
        pub dw_gold: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StorageData struct {
        dwGold uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StorageData {
        dwGold: number;
    }
    ```

