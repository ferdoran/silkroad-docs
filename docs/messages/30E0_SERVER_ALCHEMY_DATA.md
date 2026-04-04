# SERVER_ALCHEMY_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x30E0` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008735D0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwParam1` | `u32` | 4 | `0x00873603` |
| 2 | `dwParam2` | `u32` | 4 | `0x00873611` |

**Total size**: 8 bytes

### String References
| String | Type |
|--------|------|
| `PARAM_CURE_ALL` | Debug |
| `STATUS_CURE_COS` | Debug |

### Structure Summary

```
  [   0] dwParam1                       u32
  [   4] dwParam2                       u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AlchemyData {
        uint32_t dwParam1;
        uint32_t dwParam2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AlchemyData(
        uint dwParam1,
        uint dwParam2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AlchemyData {
        pub dw_param1: u32,
        pub dw_param2: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type AlchemyData struct {
        dwParam1 uint32
        dwParam2 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AlchemyData {
        dwParam1: number;
        dwParam2: number;
    }
    ```

