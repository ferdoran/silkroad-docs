# SERVER_ENTITY_SPEED_UPDATE

> **Corrected name** (server RE): Was `SERVER_PET_RESPONSE` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x30D0` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A51E0` |

### Fields (Server RE)

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `UniqueID` | `u32` | 4 | Target entity |
| 2 | `SpeedWalking` | `f32` | 4 | Walking speed |
| 3 | `SpeedRunning` | `f32` | 4 | Running speed |

**Total size**: 12 bytes

### Structure Summary

```
  [   0] UniqueID                       u32
  [   4] SpeedWalking                   f32
  [   8] SpeedRunning                   f32
```

<details>
<summary>Client Handler Reference (raw binary extraction)</summary>

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A51EE` |
| 2 | `wPetUID` | `u16` | 2 | `0x008A5203` |

> Note: Client handler data is from a different opcode's handler (misattributed during client binary analysis). The server RE fields above are authoritative.

</details>

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntitySpeedUpdate {
        uint32_t UniqueID;
        float SpeedWalking;
        float SpeedRunning;
        uint8_t byResult;
        uint16_t wPetUID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntitySpeedUpdate(
        uint UniqueID,
        float SpeedWalking,
        float SpeedRunning,
        byte byResult,
        ushort wPetUID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntitySpeedUpdate {
        pub unique_id: u32,
        pub speed_walking: f32,
        pub speed_running: f32,
        pub by_result: u8,
        pub w_pet_uid: u16,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntitySpeedUpdate struct {
        UniqueID uint32
        SpeedWalking float32
        SpeedRunning float32
        byResult uint8
        wPetUID uint16
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntitySpeedUpdate {
        uniqueID: number;
        speedWalking: number;
        speedRunning: number;
        byResult: number;
        wPetUID: number;
    }
    ```

