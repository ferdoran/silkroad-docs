# CLIENT_MOVEMENT_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB030` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D840` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwDestID` | `u32` | 4 | `0x0088D861` |
| 2 | `dwParam1` | `u32` | 4 | `0x0088D86F` |
| 3 | `dwParam2` | `u32` | 4 | `0x0088D87D` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] dwDestID                       u32
  [   4] dwParam1                       u32
  [   8] dwParam2                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MovementRequest {
        uint32_t dwDestID;
        uint32_t dwParam1;
        uint32_t dwParam2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MovementRequest(
        uint dwDestID,
        uint dwParam1,
        uint dwParam2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MovementRequest {
        pub dw_dest_id: u32,
        pub dw_param1: u32,
        pub dw_param2: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type MovementRequest struct {
        dwDestID uint32
        dwParam1 uint32
        dwParam2 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MovementRequest {
        dwDestID: number;
        dwParam1: number;
        dwParam2: number;
    }
    ```

