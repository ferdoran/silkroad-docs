# GLOBAL_HANDSHAKE

> Previously documented as `HANDSHAKE` (client-derived).

| Property | Value |
|----------|-------|
| Opcode | `0x5000` |
| Direction | Bidirectional |
| Group | Security/Handshake |
| Handler(s) | `0x004B1DA0` |

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byFlag` | `u8` | 1 | `0x004B1E06` |
| 2 | `bytesSecurity` | `bytes` | variable | `0x004B1E1B` |
| 3 | `dwClientSeed` | `u32` | 4 | `0x004B1E33` |
| 4 | `dwServerSeed` | `u32` | 4 | `0x004B1E3A` |
| 5 | `ullChallenge` | `u64` | 8 | `0x004B1E50` |

**Minimum size**: 17 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `ACTIVE_SESSION::_OnMsgReceivedBeforeHandshake() - Handshake ServerSignature Error[MsgID: 0x%x]` | Debug |
| `_OnMsgReceivedBeforeHandshake() - Initialize [MsgID: 0x%x]` | Debug |
| `SecurityModeCheck - Mode:%d, Handshake:%d` | Debug |
| `_OnMsgReceivedBeforeHandshake() - Handshake Failed:%d [MsgID: 0x%x]` | Debug |
| `_OnMsgReceivedBeforeHandshake() - Handshake Recipient Size:%d [MsgID: 0x%x]` | Debug |
| `_OnMsgReceivedBeforeHandshake() - Handshake RecipientInfo Error [MsgID: 0x%x]` | Debug |

### Structure Summary

```
  [   0] byFlag                         u8
  [   1] bytesSecurity                  bytes  (variable length)
  [   0] dwClientSeed                   u32
  [   4] dwServerSeed                   u32
  [   8] ullChallenge                   u64
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct Handshake {
        uint8_t byFlag;
        std::vector<uint8_t> bytesSecurity;
        uint32_t dwClientSeed;
        uint32_t dwServerSeed;
        uint64_t ullChallenge;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record Handshake(
        byte byFlag,
        byte[] bytesSecurity,
        uint dwClientSeed,
        uint dwServerSeed,
        ulong ullChallenge
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct Handshake {
        pub by_flag: u8,
        pub bytes_security: Vec<u8>,
        pub dw_client_seed: u32,
        pub dw_server_seed: u32,
        pub ull_challenge: u64,
    }
    ```

=== "Go"
    ```go
    // Go
    type Handshake struct {
        byFlag uint8
        bytesSecurity []byte
        dwClientSeed uint32
        dwServerSeed uint32
        ullChallenge uint64
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface Handshake {
        byFlag: number;
        bytesSecurity: Uint8Array;
        dwClientSeed: number;
        dwServerSeed: number;
        ullChallenge: bigint;
    }
    ```

