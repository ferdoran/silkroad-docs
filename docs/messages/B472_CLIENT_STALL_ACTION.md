# CLIENT_STALL_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB472` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x00899730` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0089973E` |
| 2 | `wErrorCode` | `u16` | 2 | `0x00899759` |
| 3 | `dwParam` | `u32` | 4 | `0x0089978A` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wErrorCode                     u16
  [   3] dwParam                        u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StallAction {
        uint8_t byAction;
        uint16_t wErrorCode;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StallAction(
        byte byAction,
        ushort wErrorCode,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StallAction {
        pub by_action: u8,
        pub w_error_code: u16,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type StallAction struct {
        byAction uint8
        wErrorCode uint16
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StallAction {
        byAction: number;
        wErrorCode: number;
        dwParam: number;
    }
    ```

