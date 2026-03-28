# SERVER_PARTY_INVITATION_RESPONSE

> **Corrected name** (server RE): Was `CLIENT_SIEGE_ACTION` (client-derived).
> See [server_binary_analysis.md](../server_binary_analysis.md).

| Property | Value |
|----------|-------|
| Opcode | `0xB060` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x00871D50` |
| Send site | `0x005BE7CD` (main), `0x005BE7CD` + helper `fcn.005bea90` |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `Result` | `u8` | 1 | Response result code |
| 2 | `InviterUniqueID` | `u32` | 4 | Unique ID of inviting player |
| 3 | `InviteeType` | `u8` | 1 | Type/role of invited player |
| 4 | `InviterJoinID` | `u32` | 4 | Join ID of inviter |
| 5 | `PartyID` | `u32` | 4 | Party identifier |
| 6 | `PartySettingsFlag` | `u32` | 4 | Party configuration flags |
| 7 | `PurposeType` | `u8` | 1 | Party purpose type |
| 8 | `MemberFlag` | `u8` | 1 | Member flags (role/status) |
| 9 | `InviterModelID` | `u32` | 4 | Inviter's RefObjID |

### Structure Summary

```
  [0] Result                             u8
  [1] InviterUniqueID                    u32
  [5] InviteeType                        u8
  [6] InviterJoinID                      u32
  [10] PartyID                           u32
  [14] PartySettingsFlag                 u32
  [18] PurposeType                       u8
  [19] MemberFlag                        u8
  [20] InviterModelID                    u32
```

Total payload: **24 bytes**

### Send Pattern

This packet is sent to two recipients using a helper:

```asm
; Send to player A (invitee) and player B (inviter):
push 0xB060
mov  edx, ebx            ; session A
mov  eax, edi            ; data
call fcn.005bea90         ; sends B060 to session A
push 0xB067
mov  edx, ebx
mov  eax, esi
call fcn.005bea90         ; sends B067 to session B
```

### Binary Evidence

Disassembly of write sequence starting at VA `0x5BE7CD`.
Write sizes (`eax` before each `call 0x404090`):

| Write VA | `eax` | Field |
|----------|-------|-------|
| `0x005BE7F6` | 1 | Result |
| `0x005BE807` | 4 | InviterUniqueID |
| `0x005BE871` | 1 | InviteeType |
| `0x005BE882` | 4 | InviterJoinID |
| `0x005BE90A` | 4 | PartyID |
| `0x005BE917` | 4 | PartySettingsFlag |
| `0x005BE928` | 1 | PurposeType |
| `0x005BE987` | 1 | MemberFlag |
| `0x005BE998` | 4 | InviterModelID |

Send: `mov edx, [eax + 0x27c]; call edx` at VA `0x005BE9A8`.
