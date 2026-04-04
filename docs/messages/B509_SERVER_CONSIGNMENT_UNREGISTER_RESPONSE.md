# SERVER_CONSIGNMENT_UNREGISTER_RESPONSE

> Previously documented as `CLIENT_RANKING_LIST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB509` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x008A31D0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `itemCount` | `u8` | 1 | if(packet.ReadBool() |
| 3 | `slotConsigment` | `u32` | 4 | if(packet.ReadBool() |
| 4 | `slotInventory` | `u8` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A321B` |
| 2 | `byField_02` | `u8` | 1 | `0x008A3242` |
| 3 | `byField_03` | `u8` | 1 | `0x008A3292` |
| 4 | `byField_04` | `u8` | 1 | `0x008A32A0` |
| 5 | `dwField_05` | `u32` | 4 | `0x008A32AE` |
| 6 | `dwField_06` | `u32` | 4 | `0x008A32BC` |
| 7 | `ullField_07` | `u64` | 8 | `0x008A32CA` |
| 8 | `ullField_08` | `u64` | 8 | `0x008A32D8` |
| 9 | `dwField_09` | `u32` | 4 | `0x008A32E6` |
| 10 | `wField_10` | `u16` | 2 | `0x008A3422` |

**Total size**: 34 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] byField_04                     u8
  [   4] dwField_05                     u32
  [   8] dwField_06                     u32
  [  12] ullField_07                    u64
  [  20] ullField_08                    u64
  [  28] dwField_09                     u32
  [  32] wField_10                      u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingList {
        uint8_t byResult;
        uint8_t byField_02;
        uint8_t byField_03;
        uint8_t byField_04;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint64_t ullField_07;
        uint64_t ullField_08;
        uint32_t dwField_09;
        uint16_t wField_10;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingList(
        byte byResult,
        byte byField_02,
        byte byField_03,
        byte byField_04,
        uint dwField_05,
        uint dwField_06,
        ulong ullField_07,
        ulong ullField_08,
        uint dwField_09,
        ushort wField_10
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingList {
        pub by_result: u8,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub by_field_04: u8,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub ull_field_07: u64,
        pub ull_field_08: u64,
        pub dw_field_09: u32,
        pub w_field_10: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingList struct {
        byResult uint8
        byField_02 uint8
        byField_03 uint8
        byField_04 uint8
        dwField_05 uint32
        dwField_06 uint32
        ullField_07 uint64
        ullField_08 uint64
        dwField_09 uint32
        wField_10 uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingList {
        byResult: number;
        byField_02: number;
        byField_03: number;
        byField_04: number;
        dwField_05: number;
        dwField_06: number;
        ullField_07: bigint;
        ullField_08: bigint;
        dwField_09: number;
        wField_10: number;
    }
    ```

