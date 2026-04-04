# SERVER_ENTITY_STATUS_UPDATE

> **Corrected name** (server RE): Was `SERVER_ENTITY_ACTION` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3057` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008ADF50` |

### Fields (Server RE)

Switched structure based on `UpdateType`:

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Target entity |
| 2 | `LifeState` | `u8` | 1 | `LIFESTATE_*` enum (0=Alive, 1=Dead, 2=Ghost) — from `BUF_CHARACTER_STATUS` RTTI |
| 3 | `BadStatusMask` | `u8` | 1 | Quick-access bad status bitmask for the entity at the time of the update |
| 4 | `UpdateType` | `u8` | 1 | EntityStateUpdate enum |

**UpdateType values:**

| UpdateType | Payload | Description |
|------------|---------|-------------|
| 1 (HP) | `u32 HP` | Current HP |
| 2 (MP) | `u32 MP` | Current MP |
| 3 (HPMP) | `u32 HP, u32 MP` | Current HP and MP |
| 4 (BadStatus) | `u32 BadStatusFlags` | Bad status effect flags |
| 5 (EntityHPMP) | `u32 HP, u32 MP` | Entity HP and MP |

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] LifeState                      u8        // LIFESTATE_*
  [   5] BadStatusMask                  u8
  [   6] UpdateType                     u8
  switch UpdateType:
    case 1:  [7] HP                     u32
    case 2:  [7] MP                     u32
    case 3:  [7] HP                     u32
             [11] MP                    u32
    case 4:  [7] BadStatusFlags         u32
    case 5:  [7] HP                     u32
             [11] MP                    u32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byActionType` | `u8` | 1 | `0x008ADF9A` |
| 2 | `dwActionID` | `u32` | 4 | `0x008ADFA8` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityStatusUpdate {
        uint32_t UniqueID;
        uint8_t LifeState;
        uint8_t BadStatusMask;
        uint8_t UpdateType;
        uint8_t byActionType;
        uint32_t dwActionID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityStatusUpdate(
        uint UniqueID,
        byte LifeState,
        byte BadStatusMask,
        byte UpdateType,
        byte byActionType,
        uint dwActionID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityStatusUpdate {
        pub unique_id: u32,
        pub life_state: u8,
        pub bad_status_mask: u8,
        pub update_type: u8,
        pub by_action_type: u8,
        pub dw_action_id: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityStatusUpdate struct {
        UniqueID uint32
        LifeState uint8
        BadStatusMask uint8
        UpdateType uint8
        byActionType uint8
        dwActionID uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityStatusUpdate {
        uniqueID: number;
        lifeState: number;
        badStatusMask: number;
        updateType: number;
        byActionType: number;
        dwActionID: number;
    }
    ```

