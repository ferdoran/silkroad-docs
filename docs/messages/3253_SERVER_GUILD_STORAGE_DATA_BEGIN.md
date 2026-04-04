# SERVER_GUILD_STORAGE_DATA_BEGIN

> Previously documented as `SERVER_ACADEMY_INFO` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x3253` |
| Direction | Server → Client |
| Group | Game Extended 2 |
| Handler(s) | `0x0088D160` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `gold` | `u64` | 8 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088D16E` |
| 2 | `bytesData_1` | `bytes` | variable | `0x00841948` |

**Minimum size**: 1 bytes + variable fields

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] bytesData_1                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct AcademyInfo {
        uint8_t byResult;
        std::vector<uint8_t> bytesData_1;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record AcademyInfo(
        byte byResult,
        byte[] bytesData_1
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct AcademyInfo {
        pub by_result: u8,
        pub bytes_data_1: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type AcademyInfo struct {
        byResult uint8
        bytesData_1 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface AcademyInfo {
        byResult: number;
        bytesData_1: Uint8Array;
    }
    ```

