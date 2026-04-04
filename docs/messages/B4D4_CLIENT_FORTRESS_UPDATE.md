# CLIENT_FORTRESS_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB4D4` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088E090` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byFlag1` | `u8` | 1 | `0x0088E0A3` |
| 2 | `dwUniqueID1` | `u32` | 4 | `0x0088E0BC` |
| 3 | `dwParam1` | `u32` | 4 | `0x0088E0CA` |
| 4 | `byFlag2` | `u8` | 1 | `0x0088E129` |
| 5 | `dwUniqueID2` | `u32` | 4 | `0x0088E149` |
| 6 | `dwParam2` | `u32` | 4 | `0x0088E157` |

**Total size**: 18 bytes

### Structure Summary

```
  [   0] byFlag1                        u8
  [   1] dwUniqueID1                    u32
  [   5] dwParam1                       u32
  [   9] byFlag2                        u8
  [  10] dwUniqueID2                    u32
  [  14] dwParam2                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct FortressUpdate {
        uint8_t byFlag1;
        uint32_t dwUniqueID1;
        uint32_t dwParam1;
        uint8_t byFlag2;
        uint32_t dwUniqueID2;
        uint32_t dwParam2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record FortressUpdate(
        byte byFlag1,
        uint dwUniqueID1,
        uint dwParam1,
        byte byFlag2,
        uint dwUniqueID2,
        uint dwParam2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct FortressUpdate {
        pub by_flag1: u8,
        pub dw_unique_id1: u32,
        pub dw_param1: u32,
        pub by_flag2: u8,
        pub dw_unique_id2: u32,
        pub dw_param2: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type FortressUpdate struct {
        byFlag1 uint8
        dwUniqueID1 uint32
        dwParam1 uint32
        byFlag2 uint8
        dwUniqueID2 uint32
        dwParam2 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface FortressUpdate {
        byFlag1: number;
        dwUniqueID1: number;
        dwParam1: number;
        byFlag2: number;
        dwUniqueID2: number;
        dwParam2: number;
    }
    ```

