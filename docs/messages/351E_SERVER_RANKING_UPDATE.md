# SERVER_RANKING_UPDATE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x351E` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x0089A760`, `0x0089A820` |

## Handler 1: `0x0089A760`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A76E` |
| 2 | `wField_02` | `u16` | 2 | `0x0089A783` |

**Total size**: 3 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wField_02                      u16
```

## Handler 2: `0x0089A820`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A830` |
| 2 | `byField_02` | `u8` | 1 | `0x0089A86D` |
| 3 | `byField_03` | `u8` | 1 | `0x0089A87B` |
| 4 | `dwField_04` | `u32` | 4 | `0x005F28DF` |
| 5 | `wField_05` | `u16` | 2 | `0x004F7A7D` |
| 6 | `bytesData_5` | `bytes` | variable | `0x004F7AB9` |
| 7 | `byField_07` | `u8` | 1 | `0x005F28FB` |
| 8 | `dwField_08` | `u32` | 4 | `0x005F2909` |
| 9 | `dwField_09` | `u32` | 4 | `0x005F2917` |
| 10 | `ullField_10` | `u64` | 8 | `0x005F2925` |
| 11 | `dwField_11` | `u32` | 4 | `0x005F2933` |

**Minimum size**: 30 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
  [   2] byField_03                     u8
  [   3] dwField_04                     u32
  [   7] wField_05                      u16
  [   9] bytesData_5                    bytes  (variable length)
  [   0] byField_07                     u8
  [   1] dwField_08                     u32
  [   5] dwField_09                     u32
  [   9] ullField_10                    u64
  [  17] dwField_11                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingUpdate {
        uint8_t byResult;
        uint16_t wField_02;
        uint8_t byField_02;
        uint8_t byField_03;
        uint32_t dwField_04;
        uint16_t wField_05;
        std::vector<uint8_t> bytesData_5;
        uint8_t byField_07;
        uint32_t dwField_08;
        uint32_t dwField_09;
        uint64_t ullField_10;
        uint32_t dwField_11;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingUpdate(
        byte byResult,
        ushort wField_02,
        byte byField_02,
        byte byField_03,
        uint dwField_04,
        ushort wField_05,
        byte[] bytesData_5,
        byte byField_07,
        uint dwField_08,
        uint dwField_09,
        ulong ullField_10,
        uint dwField_11
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingUpdate {
        pub by_result: u8,
        pub w_field_02: u16,
        pub by_field_02: u8,
        pub by_field_03: u8,
        pub dw_field_04: u32,
        pub w_field_05: u16,
        pub bytes_data_5: Vec<u8>,
        pub by_field_07: u8,
        pub dw_field_08: u32,
        pub dw_field_09: u32,
        pub ull_field_10: u64,
        pub dw_field_11: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingUpdate struct {
        byResult uint8
        wField_02 uint16
        byField_02 uint8
        byField_03 uint8
        dwField_04 uint32
        wField_05 uint16
        bytesData_5 []byte
        byField_07 uint8
        dwField_08 uint32
        dwField_09 uint32
        ullField_10 uint64
        dwField_11 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingUpdate {
        byResult: number;
        wField_02: number;
        byField_02: number;
        byField_03: number;
        dwField_04: number;
        wField_05: number;
        bytesData_5: Uint8Array;
        byField_07: number;
        dwField_08: number;
        dwField_09: number;
        ullField_10: bigint;
        dwField_11: number;
    }
    ```

