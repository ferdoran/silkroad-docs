# CLIENT_ENTITY_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB03C` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008A7720` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A7731` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x008A774C` |
| 3 | `byParam1` | `u8` | 1 | `0x008A775A` |
| 4 | `dwParam2` | `u32` | 4 | `0x008A7768` |
| 5 | `wParam3` | `u16` | 2 | `0x008A77F4` |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwTargetUID                    u32
  [   5] byParam1                       u8
  [   6] dwParam2                       u32
  [  10] wParam3                        u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityAction {
        uint8_t byAction;
        uint32_t dwTargetUID;
        uint8_t byParam1;
        uint32_t dwParam2;
        uint16_t wParam3;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityAction(
        byte byAction,
        uint dwTargetUID,
        byte byParam1,
        uint dwParam2,
        ushort wParam3
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityAction {
        pub by_action: u8,
        pub dw_target_uid: u32,
        pub by_param1: u8,
        pub dw_param2: u32,
        pub w_param3: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityAction struct {
        byAction uint8
        dwTargetUID uint32
        byParam1 uint8
        dwParam2 uint32
        wParam3 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityAction {
        byAction: number;
        dwTargetUID: number;
        byParam1: number;
        dwParam2: number;
        wParam3: number;
    }
    ```

