# SERVER_RANKING_INFO
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0x3514` |
| Direction | Server → Client |
| Group | Game Extended 5 |
| Handler(s) | `0x00881570` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x00881584` |
| 2 | `byField_02` | `u8` | 1 | `0x008815A3` |

**Total size**: 2 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] byField_02                     u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingInfo {
        uint8_t byResult;
        uint8_t byField_02;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingInfo(
        byte byResult,
        byte byField_02
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingInfo {
        pub by_result: u8,
        pub by_field_02: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingInfo struct {
        byResult uint8
        byField_02 uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingInfo {
        byResult: number;
        byField_02: number;
    }
    ```

