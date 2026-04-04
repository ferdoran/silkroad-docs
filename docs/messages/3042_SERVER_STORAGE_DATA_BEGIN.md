# SERVER_STORAGE_DATA_BEGIN
> **Note**: Fields below are from client binary analysis and may be inaccurate.

> **Corrected name** (server RE): Was `SERVER_ENTITY_DESPAWN` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3042` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008822C0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008822CF` |
| 2 | `byReason` | `u8` | 1 | `0x008822DD` |
| 3 | `byAnimation` | `u8` | 1 | `0x008822F9` |
| 4 | `byFlag` | `u8` | 1 | `0x00882313` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byReason                       u8
  [   5] byAnimation                    u8
  [   6] byFlag                         u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct StorageDataBegin {
        uint32_t dwUniqueID;
        uint8_t byReason;
        uint8_t byAnimation;
        uint8_t byFlag;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record StorageDataBegin(
        uint dwUniqueID,
        byte byReason,
        byte byAnimation,
        byte byFlag
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct StorageDataBegin {
        pub dw_unique_id: u32,
        pub by_reason: u8,
        pub by_animation: u8,
        pub by_flag: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type StorageDataBegin struct {
        dwUniqueID uint32
        byReason uint8
        byAnimation uint8
        byFlag uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface StorageDataBegin {
        dwUniqueID: number;
        byReason: number;
        byAnimation: number;
        byFlag: number;
    }
    ```

