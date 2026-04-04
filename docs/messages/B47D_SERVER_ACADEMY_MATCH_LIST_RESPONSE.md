# SERVER_ACADEMY_MATCH_LIST_RESPONSE

> Previously documented as `CLIENT_RANKING_DATA` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB47D` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x0088DF80` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0088DF8E` |
| 2 | `dwParam` | `u32` | 4 | `0x0088DFA9` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_PULL_DELETE` | UI |
| `UIIT_STT_TC_MACHING_DELETE` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwParam                        u32
  [   5] bytesData_2                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingData {
        uint8_t byResult;
        uint32_t dwParam;
        std::vector<uint8_t> bytesData_2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingData(
        byte byResult,
        uint dwParam,
        byte[] bytesData_2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingData {
        pub by_result: u8,
        pub dw_param: u32,
        pub bytes_data_2: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingData struct {
        byResult uint8
        dwParam uint32
        bytesData_2 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingData {
        byResult: number;
        dwParam: number;
        bytesData_2: Uint8Array;
    }
    ```

