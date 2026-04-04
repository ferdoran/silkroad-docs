# SERVER_EXCHANGE_CONFIRM_RESPONSE

> Previously documented as `CLIENT_INVENTORY_MOVE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB082` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008803F0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `bool` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008803FB` |
| 2 | `byResult` | `u8` | 1 | `0x0088043E` |

**Total size**: 5 bytes

</details>
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
    struct InventoryMove {
        uint32_t dwUniqueID;
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryMove(
        uint dwUniqueID,
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryMove {
        pub dw_unique_id: u32,
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryMove struct {
        dwUniqueID uint32
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryMove {
        dwUniqueID: number;
        byResult: number;
    }
    ```

