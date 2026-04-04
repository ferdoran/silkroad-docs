# CLIENT_ARENA_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB258` |
| Direction | Server → Client |
| Group | Client Extended 2 |
| Handler(s) | `0x00895810` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00895897` |
| 2 | `dwParam1` | `u32` | 4 | `0x008958B1` |
| 3 | `dwParam2` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwField_05` | `u32` | 4 | `0x008958CE` |

**Minimum size**: 11 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam1                       u32
  [   5] dwParam2                       u16
  [   7] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct ArenaDetail {
        uint8_t byResult;
        uint32_t dwParam1;
        uint16_t dwParam2;
        std::vector<uint8_t> bytesData_3;
        uint32_t dwField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record ArenaDetail(
        byte byResult,
        uint dwParam1,
        ushort dwParam2,
        byte[] bytesData_3,
        uint dwField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct ArenaDetail {
        pub by_result: u8,
        pub dw_param1: u32,
        pub dw_param2: u16,
        pub bytes_data_3: Vec<u8>,
        pub dw_field_05: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type ArenaDetail struct {
        byResult uint8
        dwParam1 uint32
        dwParam2 uint16
        bytesData_3 []byte
        dwField_05 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface ArenaDetail {
        byResult: number;
        dwParam1: number;
        dwParam2: number;
        bytesData_3: Uint8Array;
        dwField_05: number;
    }
    ```

