# SERVER_STALL_ENTITY_ACTION

> Previously documented as `SERVER_TELEPORT_START` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x30B7` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008721B0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `stallAction` | `u8` | 1 |  |
| 2 | `uniqueID` | `u32` | 4 | case(1) |
| 3 | `uniqueID` | `u32` | 4 | case(1) |
| 4 | `slotItemBought` | `u8` | 1 | case(1) |
| 5 | `name` | `string` | var | case(1) |
| 6 | `slotStall` | `u8` | 1 | case(1) |
| 7 | `SlotInventory` | `u8` | 1 | case(1) |
| 8 | `Quantity` | `u16` | 2 | case(1) |
| 9 | `Price` | `u64` | 8 | case(1) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTeleportID` | `u32` | 4 | `0x008721C1` |
| 2 | `wDestRegion` | `u16` | 2 | `0x008721CF` |

**Total size**: 6 bytes

</details>
### Structure Summary

```
  [   0] dwTeleportID                   u32
  [   4] wDestRegion                    u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportStart {
        uint32_t dwTeleportID;
        uint16_t wDestRegion;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportStart(
        uint dwTeleportID,
        ushort wDestRegion
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportStart {
        pub dw_teleport_id: u32,
        pub w_dest_region: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportStart struct {
        dwTeleportID uint32
        wDestRegion uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportStart {
        dwTeleportID: number;
        wDestRegion: number;
    }
    ```

