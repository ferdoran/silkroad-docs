# SERVER_ENTITY_STALL_DESTROY

> Previously documented as `SERVER_TELEPORT_DATA` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x30B9` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008720F0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `uniqueID` | `u32` | 4 |  |
| 2 | `unkUshort01` | `u16` | 2 |  |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008720FF` |
| 2 | `wRegionID` | `u16` | 2 | `0x0087216F` |
| 3 | `dwPosX` | `u32` | 4 | `0x008721C1` |
| 4 | `wAngle` | `u16` | 2 | `0x008721CF` |

**Total size**: 9 bytes

</details>
### String References
| String | Type |
|--------|------|
| `IFStall` | Debug |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] wRegionID                      u16
  [   3] dwPosX                         u32
  [   7] wAngle                         u16
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct TeleportData {
        uint8_t byResult;
        uint16_t wRegionID;
        uint32_t dwPosX;
        uint16_t wAngle;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record TeleportData(
        byte byResult,
        ushort wRegionID,
        uint dwPosX,
        ushort wAngle
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct TeleportData {
        pub by_result: u8,
        pub w_region_id: u16,
        pub dw_pos_x: u32,
        pub w_angle: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type TeleportData struct {
        byResult uint8
        wRegionID uint16
        dwPosX uint32
        wAngle uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface TeleportData {
        byResult: number;
        wRegionID: number;
        dwPosX: number;
        wAngle: number;
    }
    ```

