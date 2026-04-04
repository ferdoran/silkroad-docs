# CLIENT_STALL_CLOSE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB473` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x008997A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008997AE` |
| 2 | `wParam` | `u16` | 2 | `0x008997D5` |

**Total size**: 3 bytes

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
    struct StallClose {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallClose(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallClose {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallClose struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallClose {
        byAction: number;
        wParam: number;
    }
    ```

