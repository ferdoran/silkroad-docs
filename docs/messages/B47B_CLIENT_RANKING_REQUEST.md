# CLIENT_RANKING_REQUEST
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB47B` |
| Direction | Server → Client |
| Group | Client Extended 4 |
| Handler(s) | `0x008907F0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089082C` |
| 2 | `dwRankingID` | `u32` | 4 | `0x00890857` |
| 3 | `dwParam1` | `u32` | 4 | `0x00890865` |
| 4 | `byCategory` | `u8` | 1 | `0x00890873` |
| 5 | `dwFilterID` | `u16` | 2 | `0x0087356D` |
| 6 | `wPage` | `bytes` | variable | `0x008735A9` |
| 7 | `dwField_07` | `u32` | 4 | `0x0089088D` |
| 8 | `wField_08` | `u16` | 2 | `0x00890913` |

**Minimum size**: 18 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_STT_TC_MACHING_ENTRY` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwRankingID                    u32
  [   5] dwParam1                       u32
  [   9] byCategory                     u8
  [  10] dwFilterID                     u16
  [  12] wPage                          bytes  (variable length)
  [   0] dwField_07                     u32
  [   4] wField_08                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingRequest {
        uint8_t byResult;
        uint32_t dwRankingID;
        uint32_t dwParam1;
        uint8_t byCategory;
        uint16_t dwFilterID;
        std::vector<uint8_t> wPage;
        uint32_t dwField_07;
        uint16_t wField_08;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingRequest(
        byte byResult,
        uint dwRankingID,
        uint dwParam1,
        byte byCategory,
        ushort dwFilterID,
        byte[] wPage,
        uint dwField_07,
        ushort wField_08
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingRequest {
        pub by_result: u8,
        pub dw_ranking_id: u32,
        pub dw_param1: u32,
        pub by_category: u8,
        pub dw_filter_id: u16,
        pub w_page: Vec<u8>,
        pub dw_field_07: u32,
        pub w_field_08: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingRequest struct {
        byResult uint8
        dwRankingID uint32
        dwParam1 uint32
        byCategory uint8
        dwFilterID uint16
        wPage []byte
        dwField_07 uint32
        wField_08 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingRequest {
        byResult: number;
        dwRankingID: number;
        dwParam1: number;
        byCategory: number;
        dwFilterID: number;
        wPage: Uint8Array;
        dwField_07: number;
        wField_08: number;
    }
    ```

