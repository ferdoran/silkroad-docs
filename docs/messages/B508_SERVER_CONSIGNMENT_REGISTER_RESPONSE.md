# SERVER_CONSIGNMENT_REGISTER_RESPONSE

> Previously documented as `CLIENT_RANKING_INFO` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB508` |
| Direction | Server → Client |
| Group | Client Extended 5 |
| Handler(s) | `0x0089A9A0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `itemCount` | `u8` | 1 | if(packet.ReadBool() |
| 3 | `slotInventory` | `u8` | 1 | if(packet.ReadBool() |
| 4 | `saleStatus` | `u8` | 1 | if(packet.ReadBool() |
| 5 | `slotConsigment` | `u32` | 4 | if(packet.ReadBool() |
| 6 | `itemID` | `u32` | 4 | if(packet.ReadBool() |
| 7 | `goldDeposited` | `u64` | 8 | if(packet.ReadBool() |
| 8 | `goldSellingFee` | `u64` | 8 | if(packet.ReadBool() |
| 9 | `EndDate` | `u32` | 4 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0089A9AE` |

**Total size**: 1 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct RankingInfo {
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record RankingInfo(
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct RankingInfo {
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type RankingInfo struct {
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface RankingInfo {
        byResult: number;
    }
    ```

