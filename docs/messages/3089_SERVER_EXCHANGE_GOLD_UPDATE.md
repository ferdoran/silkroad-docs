# SERVER_EXCHANGE_GOLD_UPDATE

> Previously documented as `SERVER_INVENTORY_OPERATION` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3089` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00880520` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unkByte01` | `u8` | 1 |  |
| 2 | `gold` | `u64` | 8 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088052E` |

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
    struct InventoryOperation {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryOperation(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryOperation {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryOperation struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryOperation {
        byResult: number;
    }
    ```

