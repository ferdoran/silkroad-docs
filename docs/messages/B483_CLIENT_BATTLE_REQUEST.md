# CLIENT_BATTLE_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB483` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0089BF00` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwBattleID` | `u32` | 4 | `0x0089BF39` |

**Total size**: 4 bytes

### Structure Summary

```
  [   0] dwBattleID                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleRequest {
        uint32_t dwBattleID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleRequest(
        uint dwBattleID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleRequest {
        pub dw_battle_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleRequest struct {
        dwBattleID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleRequest {
        dwBattleID: number;
    }
    ```

