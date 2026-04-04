# SERVER_STALL_DESTROY_RESPONSE

> Previously documented as `CLIENT_PARTY_INVITE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0xB0B2` |
| Direction | Server → Client |
| Group | Game (Client→Server) |
| Handler(s) | `0x00873C10` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `dwTargetUID` | `bool` | 1 | if(packet.ReadBool() |

<details>
<summary>Original client-derived fields (may be inaccurate)</summary>

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `dwTargetUID` | `u32` | 4 | `0x00873C7D` |
| 2 | `dwAction` | `u16` | 2 | `0x004F7A7D` |
| 3 | `bytesData_2` | `bytes` | variable | `0x004F7AB9` |
| 4 | `dwField_04` | `u32` | 4 | `0x00873C97` |

**Minimum size**: 10 bytes + variable fields

</details>
### Structure Summary

```
  [   0] dwTargetUID                    u32
  [   4] dwAction                       u16
  [   6] bytesData_2                    bytes  (variable length)
  [   0] dwField_04                     u32
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct PartyInvite {
        uint32_t dwTargetUID;
        uint16_t dwAction;
        std::vector<uint8_t> bytesData_2;
        uint32_t dwField_04;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record PartyInvite(
        uint dwTargetUID,
        ushort dwAction,
        byte[] bytesData_2,
        uint dwField_04
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct PartyInvite {
        pub dw_target_uid: u32,
        pub dw_action: u16,
        pub bytes_data_2: Vec<u8>,
        pub dw_field_04: u32,
    }
    ```

=== "Go"
    ```go
    // Go
    type PartyInvite struct {
        dwTargetUID uint32
        dwAction uint16
        bytesData_2 []byte
        dwField_04 uint32
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface PartyInvite {
        dwTargetUID: number;
        dwAction: number;
        bytesData_2: Uint8Array;
        dwField_04: number;
    }
    ```

