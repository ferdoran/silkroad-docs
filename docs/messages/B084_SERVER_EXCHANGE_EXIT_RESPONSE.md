# SERVER_EXCHANGE_EXIT_RESPONSE

> Previously documented as `CLIENT_INVENTORY_DROP` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB084` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008804A0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008804AE` |

**Total size**: 1 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryDrop {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryDrop(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryDrop {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryDrop struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryDrop {
        byResult: number;
    }
    ```

