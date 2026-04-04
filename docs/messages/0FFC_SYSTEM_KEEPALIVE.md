# SYSTEM_KEEPALIVE
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x0FFC` |
| Direction | System |
| Group | System/Debug |
| Handler(s) | `0x008A5230` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTimestamp` | `u32` | 4 | `0x008A523F` |
| 2 | `byFlag` | `u8` | 1 | `0x008A524D` |
| 3 | `dwSequence` | `u32` | 4 | `0x008A5291` |
| 4 | `dwLatency` | `u32` | 4 | `0x008A529F` |
| 5 | `dwChecksum` | `u32` | 4 | `0x008A52AD` |

**Total size**: 17 bytes

### Structure Summary

```
  [   0] dwTimestamp                    u32
  [   4] byFlag                         u8
  [   5] dwSequence                     u32
  [   9] dwLatency                      u32
  [  13] dwChecksum                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct Keepalive {
        uint32_t dwTimestamp;
        uint8_t byFlag;
        uint32_t dwSequence;
        uint32_t dwLatency;
        uint32_t dwChecksum;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record Keepalive(
        uint dwTimestamp,
        byte byFlag,
        uint dwSequence,
        uint dwLatency,
        uint dwChecksum
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct Keepalive {
        pub dw_timestamp: u32,
        pub by_flag: u8,
        pub dw_sequence: u32,
        pub dw_latency: u32,
        pub dw_checksum: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type Keepalive struct {
        dwTimestamp uint32
        byFlag uint8
        dwSequence uint32
        dwLatency uint32
        dwChecksum uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface Keepalive {
        dwTimestamp: number;
        byFlag: number;
        dwSequence: number;
        dwLatency: number;
        dwChecksum: number;
    }
    ```

