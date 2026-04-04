# CLIENT_COS_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB112` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00881EC0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction1` | `u8` | 1 | `0x00881ECE` |
| 2 | `wParam1` | `u16` | 2 | `0x00881EE8` |
| 3 | `byAction2` | `u8` | 1 | `0x00881F3E` |
| 4 | `wParam2` | `u16` | 2 | `0x00881F58` |

**Total size**: 6 bytes

### Structure Summary

```
  [   0] byAction1                      u8
  [   1] wParam1                        u16
  [   3] byAction2                      u8
  [   4] wParam2                        u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosAction {
        uint8_t byAction1;
        uint16_t wParam1;
        uint8_t byAction2;
        uint16_t wParam2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosAction(
        byte byAction1,
        ushort wParam1,
        byte byAction2,
        ushort wParam2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosAction {
        pub by_action1: u8,
        pub w_param1: u16,
        pub by_action2: u8,
        pub w_param2: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosAction struct {
        byAction1 uint8
        wParam1 uint16
        byAction2 uint8
        wParam2 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosAction {
        byAction1: number;
        wParam1: number;
        byAction2: number;
        wParam2: number;
    }
    ```

