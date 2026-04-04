# SERVER_CHARACTER_DIED

> Previously documented as `SERVER_CHARACTER_LIST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3011` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008726E0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `unkByte01` | `u8` | 1 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwCharCount` | `u32` | 4 | `0x008726EE` |
| 2 | `byListType` | `u8` | 1 | `0x008726FC` |

**Total size**: 5 bytes

</details>
### Structure Summary

```
  [   0] dwCharCount                    u32
  [   4] byListType                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CharacterList {
        uint32_t dwCharCount;
        uint8_t byListType;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CharacterList(
        uint dwCharCount,
        byte byListType
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CharacterList {
        pub dw_char_count: u32,
        pub by_list_type: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CharacterList struct {
        dwCharCount uint32
        byListType uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CharacterList {
        dwCharCount: number;
        byListType: number;
    }
    ```

