# CLIENT_ALCHEMY_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB0DB` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D570` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x0088D57F` |
| 2 | `byAction` | `u8` | 1 | `0x0088D58D` |

**Total size**: 5 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byAction                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AlchemyRequest {
        uint32_t dwUniqueID;
        uint8_t byAction;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AlchemyRequest(
        uint dwUniqueID,
        byte byAction
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AlchemyRequest {
        pub dw_unique_id: u32,
        pub by_action: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type AlchemyRequest struct {
        dwUniqueID uint32
        byAction uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AlchemyRequest {
        dwUniqueID: number;
        byAction: number;
    }
    ```

