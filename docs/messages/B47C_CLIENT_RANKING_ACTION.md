# CLIENT_RANKING_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB47C` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x00890960` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089099C` |
| 2 | `dwRankingID` | `u32` | 4 | `0x008909C7` |
| 3 | `dwParam1` | `u32` | 4 | `0x008909D5` |
| 4 | `byCategory` | `u8` | 1 | `0x008909E3` |
| 5 | `wPage` | `u16` | 2 | `0x0087356D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x008735A9` |
| 7 | `wField_07` | `u16` | 2 | `0x00890A66` |

**Minimum size**: 14 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_CORRECT` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwRankingID                    u32
  [   5] dwParam1                       u32
  [   9] byCategory                     u8
  [  10] wPage                          u16
  [  12] bytesData_5                    bytes  (variable length)
  [   0] wField_07                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingAction {
        uint8_t byResult;
        uint32_t dwRankingID;
        uint32_t dwParam1;
        uint8_t byCategory;
        uint16_t wPage;
        std::vector<uint8_t> bytesData_5;
        uint16_t wField_07;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingAction(
        byte byResult,
        uint dwRankingID,
        uint dwParam1,
        byte byCategory,
        ushort wPage,
        byte[] bytesData_5,
        ushort wField_07
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingAction {
        pub by_result: u8,
        pub dw_ranking_id: u32,
        pub dw_param1: u32,
        pub by_category: u8,
        pub w_page: u16,
        pub bytes_data_5: Vec<u8>,
        pub w_field_07: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingAction struct {
        byResult uint8
        dwRankingID uint32
        dwParam1 uint32
        byCategory uint8
        wPage uint16
        bytesData_5 []byte
        wField_07 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingAction {
        byResult: number;
        dwRankingID: number;
        dwParam1: number;
        byCategory: number;
        wPage: number;
        bytesData_5: Uint8Array;
        wField_07: number;
    }
    ```

