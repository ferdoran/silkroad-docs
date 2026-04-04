# SERVER_STORAGE_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30CD` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A7630` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A763F` |
| 2 | `byResult` | `u8` | 1 | `0x008A764D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StorageResponse {
        uint32_t dwUniqueID;
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StorageResponse(
        uint dwUniqueID,
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StorageResponse {
        pub dw_unique_id: u32,
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type StorageResponse struct {
        dwUniqueID uint32
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StorageResponse {
        dwUniqueID: number;
        byResult: number;
    }
    ```

