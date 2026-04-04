# SERVER_STORAGE_DATA

> Previously documented as `SERVER_ENTITY_PICKUP` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3049` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A74F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `ullTargetUID` | `u64` | 8 | `0x008A7525` |

**Total size**: 8 bytes

### Structure Summary

```
  [   0] ullTargetUID                   u64
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityPickup {
        uint64_t ullTargetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityPickup(
        ulong ullTargetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityPickup {
        pub ull_target_uid: u64,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityPickup struct {
        ullTargetUID uint64
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityPickup {
        ullTargetUID: bigint;
    }
    ```

