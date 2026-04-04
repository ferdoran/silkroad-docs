# CLIENT_RANKING_ENTRY
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB50A` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089AB50` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089AB5E` |
| 2 | `byField_02` | `u8` | 1 | `0x0089AB9E` |
| 3 | `wField_03` | `u16` | 2 | `0x004F7A7D` |
| 4 | `bytesData_3` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwField_05` | `u32` | 4 | `0x005ED4D5` |
| 6 | `dwField_06` | `u32` | 4 | `0x008BE549` |
| 7 | `byField_07` | `u8` | 1 | `0x008BE5DD` |
| 8 | `ullField_08` | `u64` | 8 | `0x008BE5ED` |
| 9 | `dwField_09` | `u32` | 4 | `0x008BE5FB` |
| 10 | `bytesData_9` | `bytes` | variable | `0x008BE642` |
| 11 | `ullField_11` | `u64` | 8 | `0x008BE652` |
| 12 | `dwField_12` | `u32` | 4 | `0x008BE662` |
| 13 | `wField_13` | `u16` | 2 | `0x008BE6C9` |
| 14 | `wField_14` | `u16` | 2 | `0x008BE75F` |
| 15 | `byField_15` | `u8` | 1 | `0x008BE830` |
| 16 | `dwField_16` | `u32` | 4 | `0x008BE849` |
| 17 | `dwField_17` | `u32` | 4 | `0x008BE8F9` |
| 18 | `byField_18` | `u8` | 1 | `0x008BE927` |
| 19 | `byField_19` | `u8` | 1 | `0x008BE97D` |
| 20 | `dwField_20` | `u32` | 4 | `0x008BE98B` |
| 21 | `dwField_21` | `u32` | 4 | `0x008BE999` |
| 22 | `dwField_22` | `u32` | 4 | `0x008BE9DA` |
| 23 | `byField_23` | `u8` | 1 | `0x008BE9E8` |
| 24 | `dwField_24` | `u32` | 4 | `0x008BEAAE` |

**Minimum size**: 69 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] wField_03                      u16
  [   4] bytesData_3                    bytes  (variable length)
  [   0] dwField_05                     u32
  [   4] dwField_06                     u32
  [   8] byField_07                     u8
  [   9] ullField_08                    u64
  [  17] dwField_09                     u32
  [  21] bytesData_9                    bytes  (variable length)
  [   0] ullField_11                    u64
  [   8] dwField_12                     u32
  [  12] wField_13                      u16
  [  14] wField_14                      u16
  [  16] byField_15                     u8
  [  17] dwField_16                     u32
  [  21] dwField_17                     u32
  [  25] byField_18                     u8
  [  26] byField_19                     u8
  [  27] dwField_20                     u32
  [  31] dwField_21                     u32
  [  35] dwField_22                     u32
  [  39] byField_23                     u8
  [  40] dwField_24                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingEntry {
        uint8_t byResult;
        uint8_t byField_02;
        uint16_t wField_03;
        std::vector<uint8_t> bytesData_3;
        uint32_t dwField_05;
        uint32_t dwField_06;
        uint8_t byField_07;
        uint64_t ullField_08;
        uint32_t dwField_09;
        std::vector<uint8_t> bytesData_9;
        uint64_t ullField_11;
        uint32_t dwField_12;
        uint16_t wField_13;
        uint16_t wField_14;
        uint8_t byField_15;
        uint32_t dwField_16;
        uint32_t dwField_17;
        uint8_t byField_18;
        uint8_t byField_19;
        uint32_t dwField_20;
        uint32_t dwField_21;
        uint32_t dwField_22;
        uint8_t byField_23;
        uint32_t dwField_24;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingEntry(
        byte byResult,
        byte byField_02,
        ushort wField_03,
        byte[] bytesData_3,
        uint dwField_05,
        uint dwField_06,
        byte byField_07,
        ulong ullField_08,
        uint dwField_09,
        byte[] bytesData_9,
        ulong ullField_11,
        uint dwField_12,
        ushort wField_13,
        ushort wField_14,
        byte byField_15,
        uint dwField_16,
        uint dwField_17,
        byte byField_18,
        byte byField_19,
        uint dwField_20,
        uint dwField_21,
        uint dwField_22,
        byte byField_23,
        uint dwField_24
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingEntry {
        pub by_result: u8,
        pub by_field_02: u8,
        pub w_field_03: u16,
        pub bytes_data_3: Vec<u8>,
        pub dw_field_05: u32,
        pub dw_field_06: u32,
        pub by_field_07: u8,
        pub ull_field_08: u64,
        pub dw_field_09: u32,
        pub bytes_data_9: Vec<u8>,
        pub ull_field_11: u64,
        pub dw_field_12: u32,
        pub w_field_13: u16,
        pub w_field_14: u16,
        pub by_field_15: u8,
        pub dw_field_16: u32,
        pub dw_field_17: u32,
        pub by_field_18: u8,
        pub by_field_19: u8,
        pub dw_field_20: u32,
        pub dw_field_21: u32,
        pub dw_field_22: u32,
        pub by_field_23: u8,
        pub dw_field_24: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingEntry struct {
        byResult uint8
        byField_02 uint8
        wField_03 uint16
        bytesData_3 []byte
        dwField_05 uint32
        dwField_06 uint32
        byField_07 uint8
        ullField_08 uint64
        dwField_09 uint32
        bytesData_9 []byte
        ullField_11 uint64
        dwField_12 uint32
        wField_13 uint16
        wField_14 uint16
        byField_15 uint8
        dwField_16 uint32
        dwField_17 uint32
        byField_18 uint8
        byField_19 uint8
        dwField_20 uint32
        dwField_21 uint32
        dwField_22 uint32
        byField_23 uint8
        dwField_24 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingEntry {
        byResult: number;
        byField_02: number;
        wField_03: number;
        bytesData_3: Uint8Array;
        dwField_05: number;
        dwField_06: number;
        byField_07: number;
        ullField_08: bigint;
        dwField_09: number;
        bytesData_9: Uint8Array;
        ullField_11: bigint;
        dwField_12: number;
        wField_13: number;
        wField_14: number;
        byField_15: number;
        dwField_16: number;
        dwField_17: number;
        byField_18: number;
        byField_19: number;
        dwField_20: number;
        dwField_21: number;
        dwField_22: number;
        byField_23: number;
        dwField_24: number;
    }
    ```

