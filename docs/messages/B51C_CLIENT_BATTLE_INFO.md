# CLIENT_BATTLE_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB51C` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089A6C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A6CE` |
| 2 | `wField_02` | `u16` | 2 | `0x0089A6E3` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct BattleInfo {
        uint8_t byResult;
        uint16_t wField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record BattleInfo(
        byte byResult,
        ushort wField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct BattleInfo {
        pub by_result: u8,
        pub w_field_02: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type BattleInfo struct {
        byResult uint8
        wField_02 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface BattleInfo {
        byResult: number;
        wField_02: number;
    }
    ```

