# SERVER_ENTITY_STALL_CREATE

> Previously documented as `SERVER_TELEPORT_READY` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x30B8` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00872040` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `uniqueID` | `u32` | 4 |  |
| 2 | `Title` | `string` | var |  |
| 3 | `DecorationID` | `u32` | 4 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byReady` | `u8` | 1 | `0x0087204F` |

**Total size**: 1 bytes

</details>
### Structure Summary

```
  [   0] byReady                        u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportReady {
        uint8_t byReady;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportReady(
        byte byReady
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportReady {
        pub by_ready: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportReady struct {
        byReady uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportReady {
        byReady: number;
    }
    ```

