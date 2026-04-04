# CLIENT_COS_DATA
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB113` |
| Direction | Server → Client |
| Group | Client Extended |
| Handler(s) | `0x00885AE0`, `0x00881F80` |

## Handler 1: `0x00885AE0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00885B0F` |
| 2 | `dwParam` | `u32` | 4 | `0x00885B25` |

**Total size**: 5 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_CTL_GUILDWAR_NOTCOMPENSATION` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam                        u32
```

## Handler 2: `0x00881F80`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881F8E` |
| 2 | `dwParam` | `u16` | 2 | `0x00881FA8` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_CTL_GUILDWAR_NOTCOMPENSATION` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam                        u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct CosData {
        uint8_t byResult;
        uint32_t dwParam;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record CosData(
        byte byResult,
        uint dwParam
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct CosData {
        pub by_result: u8,
        pub dw_param: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type CosData struct {
        byResult uint8
        dwParam uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface CosData {
        byResult: number;
        dwParam: number;
    }
    ```

