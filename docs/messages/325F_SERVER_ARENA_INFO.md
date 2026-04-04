# SERVER_ARENA_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x325F` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x00899F40` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00899F71` |
| 2 | `wField_02` | `u16` | 2 | `0x00899F92` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_AVATAR_MAGICOPTION_ADD` | UI |

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
    struct ArenaInfo {
        uint8_t byResult;
        uint16_t wField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaInfo(
        byte byResult,
        ushort wField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaInfo {
        pub by_result: u8,
        pub w_field_02: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaInfo struct {
        byResult uint8
        wField_02 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaInfo {
        byResult: number;
        wField_02: number;
    }
    ```

