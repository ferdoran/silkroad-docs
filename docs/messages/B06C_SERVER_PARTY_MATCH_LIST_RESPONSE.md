# SERVER_PARTY_MATCH_LIST_RESPONSE

> Previously documented as `CLIENT_ENTITY_DESPAWN_REQUEST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB06C` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x008801E0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `pageCount` | `u8` | 1 | if(packet.ReadBool() |
| 3 | `pageIndex` | `u8` | 1 | if(packet.ReadBool() |
| 4 | `partyCount` | `u8` | 1 | if(packet.ReadBool() |
| 5 | `Number` | `u32` | 4 | if(packet.ReadBool() |
| 6 | `MasterJoinID` | `u32` | 4 | if(packet.ReadBool() |
| 7 | `MasterName` | `string` | var | if(packet.ReadBool() |
| 8 | `RaceType` | `u8` | 1 | if(packet.ReadBool() |
| 9 | `MemberCount` | `u8` | 1 | if(packet.ReadBool() |
| 10 | `Setup` | `u8` | 1 | if(packet.ReadBool() |
| 11 | `Purpose` | `u8` | 1 | if(packet.ReadBool() |
| 12 | `LevelMin` | `u8` | 1 | if(packet.ReadBool() |
| 13 | `LevelMax` | `u8` | 1 | if(packet.ReadBool() |
| 14 | `Title` | `string` | var | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008801EE` |
| 2 | `dwTargetUID` | `u32` | 4 | `0x0088020A` |
| 3 | `bytesData_2` | `bytes` | variable | `0x00841948` |

**Minimum size**: 5 bytes + variable fields

</details>
### String References
| String | Type |
|--------|------|
| `UIIT_MSG_PARTYMATCH_DELETE_COMPLETE` | UI |
| `UIIT_MSG_PARTYMATCH_DELETE_COMPLETE2` | UI |

### Structure Summary

```
  [   0] byResult                       u8
  [   1] dwTargetUID                    u32
  [   5] bytesData_2                    bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct EntityDespawnRequest {
        uint8_t byResult;
        uint32_t dwTargetUID;
        std::vector<uint8_t> bytesData_2;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record EntityDespawnRequest(
        byte byResult,
        uint dwTargetUID,
        byte[] bytesData_2
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct EntityDespawnRequest {
        pub by_result: u8,
        pub dw_target_uid: u32,
        pub bytes_data_2: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type EntityDespawnRequest struct {
        byResult uint8
        dwTargetUID uint32
        bytesData_2 []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface EntityDespawnRequest {
        byResult: number;
        dwTargetUID: number;
        bytesData_2: Uint8Array;
    }
    ```

