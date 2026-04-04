# CLIENT_STALL_CONFIRM
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB478` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x00899940` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0089994E` |
| 2 | `wParam` | `u16` | 2 | `0x00899987` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_TC_COMMON_KNOW_REMIND_UPDATE` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallConfirm {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallConfirm(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallConfirm {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallConfirm struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallConfirm {
        byAction: number;
        wParam: number;
    }
    ```

