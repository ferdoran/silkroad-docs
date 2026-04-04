# SERVER_STALL_UPDATE_RESPONSE

> Previously documented as `CLIENT_GUILD_REQUEST` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB0BA` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00872500`, `0x00873D60` |

## Handler 1: `0x00872500`

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `byResult` | `bool` | 1 | if(packet.ReadBool() |
| 2 | `type` | `u8` | 1 | if(packet.ReadBool() |
| 3 | `slotStall` | `u8` | 1 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 4 | `quantity` | `u16` | 2 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 5 | `price` | `u64` | 8 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 6 | `errCode` | `u16` | 2 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 7 | `errorCode` | `u16` | 2 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 8 | `slotStall` | `u8` | 1 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 9 | `SlotInventory` | `u8` | 1 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 10 | `Quantity` | `u16` | 2 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 11 | `Price` | `u64` | 8 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 12 | `unk` | `bool` | 1 | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |
| 13 | `unk` | `string` | var | if(packet.ReadBool() → case(SRTypes.StallUpdate.ItemUpdate) |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u8` | 1 | `0x0087250E` |
| 2 | `byConfirm` | `u8` | 1 | `0x00872532` |

**Total size**: 2 bytes

</details>
### Structure Summary

```
  [   0] byResult                       u8
  [   1] byConfirm                      u8
```

## Handler 2: `0x00873D60`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byResult` | `u32` | 4 | `0x00873DCA` |
| 2 | `byConfirm` | `u16` | 2 | `0x004F7A7D` |
| 3 | `dwUniqueID` | `bytes` | variable | `0x004F7AB9` |

**Minimum size**: 6 bytes + variable fields

### Structure Summary

```
  [   0] byResult                       u32
  [   4] byConfirm                      u16
  [   6] dwUniqueID                     bytes  (variable length)
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildRequest {
        uint8_t byResult;
        uint8_t byConfirm;
        std::vector<uint8_t> dwUniqueID;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildRequest(
        byte byResult,
        byte byConfirm,
        byte[] dwUniqueID
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildRequest {
        pub by_result: u8,
        pub by_confirm: u8,
        pub dw_unique_id: Vec<u8>,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildRequest struct {
        byResult uint8
        byConfirm uint8
        dwUniqueID []byte
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildRequest {
        byResult: number;
        byConfirm: number;
        dwUniqueID: Uint8Array;
    }
    ```

