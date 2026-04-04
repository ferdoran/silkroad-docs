# CLIENT_RANKING_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB507` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x008A38A0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A38EB` |
| 2 | `byField_02` | `u8` | 1 | `0x008A3912` |
| 3 | `dwField_03` | `u32` | 4 | `0x008A397C` |
| 4 | `byField_04` | `u8` | 1 | `0x008A398A` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A3998` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A39A6` |
| 7 | `ullField_07` | `u64` | 8 | `0x008A39B4` |
| 8 | `ullField_08` | `u64` | 8 | `0x008A39C2` |
| 9 | `ullField_09` | `u64` | 8 | `0x008A39D0` |
| 10 | `dwField_10` | `u32` | 4 | `0x008A39DE` |
| 11 | `wField_11` | `u16` | 2 | `0x008A3FBF` |

**Total size**: 45 bytes

### String References
| String | Type |
|--------|------|
| `ERROR - pOpenMarketRegistrationWnd != NULL` | Debug |
| `UIIT_STT_OPEN_MARKET_SELL` | UI |
| `UIIT_STT_OPEN_MARKET_DELETE_WARNING` | UI |
| `UIIT_STT_OPEN_MARKET_SELL_TIME_OVER` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] dwField_03                     u32
  [   6] byField_04                     u8
  [   7] dwField_05                     u32
  [  11] dwField_06                     u32
  [  15] ullField_07                    u64
  [  23] ullField_08                    u64
  [  31] ullField_09                    u64
  [  39] dwField_10                     u32
  [  43] wField_11                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingUpdate {
        uint8_t byResult;
        uint8_t byField_02;
        uint32_t dwField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint64_t ullField_07;
        uint64_t ullField_08;
        uint64_t ullField_09;
        uint32_t dwField_10;
        uint16_t wField_11;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingUpdate(
        byte byResult,
        byte byField_02,
        uint dwField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06,
        ulong ullField_07,
        ulong ullField_08,
        ulong ullField_09,
        uint dwField_10,
        ushort wField_11
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingUpdate {
        pub by_result: u8,
        pub by_field_02: u8,
        pub dw_field_03: u32,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub ull_field_07: u64,
        pub ull_field_08: u64,
        pub ull_field_09: u64,
        pub dw_field_10: u32,
        pub w_field_11: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingUpdate struct {
        byResult uint8
        byField_02 uint8
        dwField_03 uint32
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
        ullField_07 uint64
        ullField_08 uint64
        ullField_09 uint64
        dwField_10 uint32
        wField_11 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingUpdate {
        byResult: number;
        byField_02: number;
        dwField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
        ullField_07: bigint;
        ullField_08: bigint;
        ullField_09: bigint;
        dwField_10: number;
        wField_11: number;
    }
    ```

