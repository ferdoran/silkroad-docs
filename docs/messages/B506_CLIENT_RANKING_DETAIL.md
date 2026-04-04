# CLIENT_RANKING_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB506` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x008A3470` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008A34BB` |
| 2 | `dwField_02` | `u32` | 4 | `0x008A350B` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A3519` |
| 4 | `byField_04` | `u8` | 1 | `0x008A3527` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A3535` |

**Total size**: 14 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_STT_OPEN_MARKET_SELL` | UI |
| `UIIT_STT_OPEN_MARKET_SELL_TIME_OVER` | UI |
| `UIIT_STT_OPEN_MARKET_ITEM_DELETE` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] dwField_02                     u32
  [   5] dwField_03                     u32
  [   9] byField_04                     u8
  [  10] dwField_05                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingDetail {
        uint8_t byAction;
        uint32_t dwField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingDetail(
        byte byAction,
        uint dwField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingDetail {
        pub by_action: u8,
        pub dw_field_02: u32,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingDetail struct {
        byAction uint8
        dwField_02 uint32
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingDetail {
        byAction: number;
        dwField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
    }
    ```

