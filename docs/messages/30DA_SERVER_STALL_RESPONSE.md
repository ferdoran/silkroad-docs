# SERVER_STALL_RESPONSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30DA` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x0088DAD0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DADF` |
| 2 | `dwStallUID` | `u32` | 4 | `0x0088DB05` |
| 3 | `dwGold` | `u32` | 4 | `0x0088DB13` |

**Total size**: 9 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwStallUID                     u32
  [   5] dwGold                         u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallResponse {
        uint8_t byResult;
        uint32_t dwStallUID;
        uint32_t dwGold;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallResponse(
        byte byResult,
        uint dwStallUID,
        uint dwGold
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallResponse {
        pub by_result: u8,
        pub dw_stall_uid: u32,
        pub dw_gold: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallResponse struct {
        byResult uint8
        dwStallUID uint32
        dwGold uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallResponse {
        byResult: number;
        dwStallUID: number;
        dwGold: number;
    }
    ```

