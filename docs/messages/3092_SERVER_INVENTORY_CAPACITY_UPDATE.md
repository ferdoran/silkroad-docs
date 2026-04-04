# SERVER_INVENTORY_CAPACITY_UPDATE

> **Corrected name** (server RE): Was `SERVER_PARTY_INFO` (client-derived). See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0x3092` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A8EA0` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `newCapacity` | `u8` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x008A8ED2` |
| 2 | `wMemberCount` | `u16` | 2 | `0x008A8EEB` |
| 3 | `bytesMemberData` | `bytes` | variable | `0x008416B1` |
| 4 | `bytesPartyData` | `bytes` | variable | `0x00841948` |

**Minimum size**: 3 bytes + variable fields

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] wMemberCount                   u16
  [   3] bytesMemberData                bytes  (variable length)
  [   0] bytesPartyData                 bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct InventoryCapacityUpdate {
        uint8_t byResult;
        uint16_t wMemberCount;
        std::vector<uint8_t> bytesMemberData;
        std::vector<uint8_t> bytesPartyData;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record InventoryCapacityUpdate(
        byte byResult,
        ushort wMemberCount,
        byte[] bytesMemberData,
        byte[] bytesPartyData
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct InventoryCapacityUpdate {
        pub by_result: u8,
        pub w_member_count: u16,
        pub bytes_member_data: Vec<u8>,
        pub bytes_party_data: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type InventoryCapacityUpdate struct {
        byResult uint8
        wMemberCount uint16
        bytesMemberData []byte
        bytesPartyData []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface InventoryCapacityUpdate {
        byResult: number;
        wMemberCount: number;
        bytesMemberData: Uint8Array;
        bytesPartyData: Uint8Array;
    }
    ```

