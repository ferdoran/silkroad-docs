# SERVER_GUILD_STORAGE_RESPONSE

> Previously documented as `CLIENT_ACADEMY_UPDATE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB250` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x0088D5C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D5CE` |
| 2 | `dwParam` | `u32` | 4 | `0x0088D5E3` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_QUEST_GET_ITEM_FAILURE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyUpdate {
        uint8_t byResult;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyUpdate(
        byte byResult,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyUpdate {
        pub by_result: u8,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyUpdate struct {
        byResult uint8
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyUpdate {
        byResult: number;
        dwParam: number;
    }
    ```

