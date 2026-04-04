# CLIENT_COS_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB116` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x008A7690`, `0x008A7B80` |

## Handler 1: `0x008A7690`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u32` | 4 | `0x008A76A1` |
| 2 | `byFlag1` | `u8` | 1 | `0x008A76AF` |
| 3 | `byFlag2` | `u8` | 1 | `0x008A76D5` |
| 4 | `byExtra` | `u8` | 1 | `0x008A76F9` |

**Total size**: 7 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u32
  [   4] byFlag1                        u8
  [   5] byFlag2                        u8
  [   6] byExtra                        u8
```

## Handler 2: `0x008A7B80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwUniqueID` | `u8` | 1 | `0x008A7B8E` |
| 2 | `byFlag1` | `u16` | 2 | `0x008A7BA8` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] dwUniqueID                     u8
  [   1] byFlag1                        u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosInfo {
        uint32_t dwUniqueID;
        uint8_t byFlag1;
        uint8_t byFlag2;
        uint8_t byExtra;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosInfo(
        uint dwUniqueID,
        byte byFlag1,
        byte byFlag2,
        byte byExtra
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosInfo {
        pub dw_unique_id: u32,
        pub by_flag1: u8,
        pub by_flag2: u8,
        pub by_extra: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosInfo struct {
        dwUniqueID uint32
        byFlag1 uint8
        byFlag2 uint8
        byExtra uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosInfo {
        dwUniqueID: number;
        byFlag1: number;
        byFlag2: number;
        byExtra: number;
    }
    ```

