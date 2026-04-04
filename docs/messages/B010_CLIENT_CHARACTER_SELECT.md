# CLIENT_CHARACTER_SELECT
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB010` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A7A20` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A7A2E` |
| 2 | `wCharIndex` | `u16` | 2 | `0x008A7A43` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wCharIndex                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterSelect {
        uint8_t byResult;
        uint16_t wCharIndex;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterSelect(
        byte byResult,
        ushort wCharIndex
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterSelect {
        pub by_result: u8,
        pub w_char_index: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterSelect struct {
        byResult uint8
        wCharIndex uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterSelect {
        byResult: number;
        wCharIndex: number;
    }
    ```

