# CLIENT_COS_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB114` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00881F30` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x00881F3E` |
| 2 | `wParam` | `u16` | 2 | `0x00881F58` |

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
    struct CosUpdate {
        uint8_t byAction;
        uint16_t wParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosUpdate(
        byte byAction,
        ushort wParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosUpdate {
        pub by_action: u8,
        pub w_param: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosUpdate struct {
        byAction uint8
        wParam uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosUpdate {
        byAction: number;
        wParam: number;
    }
    ```

