# SERVER_CHAT_SYSTEM
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x7030` |
| Direction | Client → Server |
| Group | Chat/Social |
| Handler(s) | `0x0088DA80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DA8E` |
| 2 | `wField_02` | `u16` | 2 | `0x0088DAA3` |

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
    struct ChatSystem {
        uint8_t byResult;
        uint16_t wField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ChatSystem(
        byte byResult,
        ushort wField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ChatSystem {
        pub by_result: u8,
        pub w_field_02: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type ChatSystem struct {
        byResult uint8
        wField_02 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ChatSystem {
        byResult: number;
        wField_02: number;
    }
    ```

