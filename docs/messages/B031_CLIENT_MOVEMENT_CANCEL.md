# CLIENT_MOVEMENT_CANCEL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB031` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x0088D8C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byType` | `u8` | 1 | `0x0088D8CE` |
| 2 | `wParam` | `u16` | 2 | `0x0088D8E8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byType                         u8
  [   1] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct MovementCancel {
        uint8_t byType;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record MovementCancel(
        byte byType,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct MovementCancel {
        pub by_type: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type MovementCancel struct {
        byType uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface MovementCancel {
        byType: number;
        wParam: number;
    }
    ```

