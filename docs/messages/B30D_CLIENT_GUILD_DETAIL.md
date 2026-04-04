# CLIENT_GUILD_DETAIL
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB30D` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x008A1360` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A1378` |
| 2 | `wCategoryID` | `u16` | 2 | `0x008A1392` |
| 3 | `byHasItems` | `u8` | 1 | `0x008A13A0` |
| 4 | `dwPageID` | `u32` | 4 | `0x008A13C3` |
| 5 | `wItemCount` | `u16` | 2 | `0x008A13D1` |

**Total size**: 10 bytes

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wCategoryID                    u16
  [   3] byHasItems                     u8
  [   4] dwPageID                       u32
  [   8] wItemCount                     u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildDetail {
        uint8_t byResult;
        uint16_t wCategoryID;
        uint8_t byHasItems;
        uint32_t dwPageID;
        uint16_t wItemCount;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildDetail(
        byte byResult,
        ushort wCategoryID,
        byte byHasItems,
        uint dwPageID,
        ushort wItemCount
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildDetail {
        pub by_result: u8,
        pub w_category_id: u16,
        pub by_has_items: u8,
        pub dw_page_id: u32,
        pub w_item_count: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildDetail struct {
        byResult uint8
        wCategoryID uint16
        byHasItems uint8
        dwPageID uint32
        wItemCount uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildDetail {
        byResult: number;
        wCategoryID: number;
        byHasItems: number;
        dwPageID: number;
        wItemCount: number;
    }
    ```

