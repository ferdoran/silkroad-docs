# CLIENT_GUILD_ACTION
> **Note**: Fields below are from client binary analysis and may be inaccurate.

| Property | Value |
|----------|-------|
| Opcode | `0xB30A` |
| Direction | Server → Client |
| Group | Client Extended 3 |
| Handler(s) | `0x008820B0`, `0x00886310` |

## Handler 1: `0x008820B0`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x008820BE` |
| 2 | `wParam` | `u16` | 2 | `0x008820F5` |

**Total size**: 3 bytes

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_LETTER_SENDOK` | UI |

### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `UIIT_MSG_FRIEND_CONNECT` | UI |
| `UIIT_MSG_FRIEND_DISCONNECT` | UI |
| `UIIT_MSG_LETTERERR_UNKNOWNLETTER` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u16
```

## Handler 2: `0x00886310`

### Fields

| # | Name | Type | Size | Read Address |
|---|------|------|------|-------------|
| 1 | `byAction` | `u8` | 1 | `0x0088635A` |
| 2 | `wParam` | `u32` | 4 | `0x008863A1` |
| 3 | `byType` | `u16` | 2 | `0x004F7A7D` |
| 4 | `dwMemberUID1` | `bytes` | variable | `0x004F7AB9` |
| 5 | `dwMemberUID2` | `u32` | 4 | `0x008863BB` |
| 6 | `dwFriendUID` | `u32` | 4 | `0x0088645A` |
| 7 | `dwParam` | `u32` | 4 | `0x00886499` |
| 8 | `byOnlineFlag` | `u8` | 1 | `0x008864A7` |
| 9 | `dwExtraUID` | `u32` | 4 | `0x00886667` |
| 10 | `dwAssocUID` | `u32` | 4 | `0x00886675` |
| 11 | `byResult` | `u8` | 1 | `0x00886710` |

**Minimum size**: 29 bytes + variable fields

### String References
| String | Type |
|--------|------|
| `UIIT_MSG_LETTER_SENDOK` | UI |

### String References
| String | Type |
|--------|------|
| `D:\\vss-od\\Silkroad\\Client\\client\\NetProcessInInterface.cpp` | Debug |
| `UIIT_MSG_FRIEND_CONNECT` | UI |
| `UIIT_MSG_FRIEND_DISCONNECT` | UI |
| `UIIT_MSG_LETTERERR_UNKNOWNLETTER` | UI |

### Structure Summary

```
  [   0] byAction                       u8
  [   1] wParam                         u32
  [   5] byType                         u16
  [   7] dwMemberUID1                   bytes  (variable length)
  [   0] dwMemberUID2                   u32
  [   4] dwFriendUID                    u32
  [   8] dwParam                        u32
  [  12] byOnlineFlag                   u8
  [  13] dwExtraUID                     u32
  [  17] dwAssocUID                     u32
  [  21] byResult                       u8
```

---

### Struct Definitions

=== "C++"
    ```cpp
    // C++  (SRO wire types; use your serialisation layer for endianness)
    struct GuildAction {
        uint8_t byAction;
        uint16_t wParam;
        uint16_t byType;
        std::vector<uint8_t> dwMemberUID1;
        uint32_t dwMemberUID2;
        uint32_t dwFriendUID;
        uint32_t dwParam;
        uint8_t byOnlineFlag;
        uint32_t dwExtraUID;
        uint32_t dwAssocUID;
        uint8_t byResult;
    };
    ```

=== "C#"
    ```csharp
    // C#
    public record GuildAction(
        byte byAction,
        ushort wParam,
        ushort byType,
        byte[] dwMemberUID1,
        uint dwMemberUID2,
        uint dwFriendUID,
        uint dwParam,
        byte byOnlineFlag,
        uint dwExtraUID,
        uint dwAssocUID,
        byte byResult
    );
    ```

=== "Rust"
    ```rust
    // Rust
    pub struct GuildAction {
        pub by_action: u8,
        pub w_param: u16,
        pub by_type: u16,
        pub dw_member_uid1: Vec<u8>,
        pub dw_member_uid2: u32,
        pub dw_friend_uid: u32,
        pub dw_param: u32,
        pub by_online_flag: u8,
        pub dw_extra_uid: u32,
        pub dw_assoc_uid: u32,
        pub by_result: u8,
    }
    ```

=== "Go"
    ```go
    // Go
    type GuildAction struct {
        byAction uint8
        wParam uint16
        byType uint16
        dwMemberUID1 []byte
        dwMemberUID2 uint32
        dwFriendUID uint32
        dwParam uint32
        byOnlineFlag uint8
        dwExtraUID uint32
        dwAssocUID uint32
        byResult uint8
    }
    ```

=== "TypeScript"
    ```typescript
    // TypeScript
    export interface GuildAction {
        byAction: number;
        wParam: number;
        byType: number;
        dwMemberUID1: Uint8Array;
        dwMemberUID2: number;
        dwFriendUID: number;
        dwParam: number;
        byOnlineFlag: number;
        dwExtraUID: number;
        dwAssocUID: number;
        byResult: number;
    }
    ```

