# SERVER_SKILL_DATA

| Property | Value |
|----------|-------|
| Opcode | `0x30C3` |
| Direction | Server → Client |
| Group | Game (Server→Client) |
| Handler(s) | `0x008A9000` |

### Fields

No payload structure could be recovered from static analysis.

The opcode `0x30C3` does not appear as a direct `PUSH` instruction in SR_GameServer.exe
or any of the analyzed plugin DLLs. Possible explanations:

- **Computed opcode**: The opcode may be derived at runtime
  (e.g. `0x30C0 | type`, where `type = 3` gives `0x30C3`).
- **Plugin or extension**: May be sent from a module not present in the analyzed binaries.
- **Rarely triggered path**: Could be guarded behind a feature flag.

### Related Opcodes

| Opcode | Name | Notes |
|--------|------|-------|
| `0x30C8` | `SERVER_PET_DATA` | COS/pet data (same 0x30Cx range) |
| `0x30C9` | `SERVER_PET_UPDATE` | Pet update |
| `0x30C3` | `SERVER_SKILL_DATA` (this) | Unknown structure |

### Investigation Status

Searched in: SR_GameServer.exe (clean), GatewayServer.exe, AgentServer.exe,
SR_ShardManager.exe, all SMPlugin DLLs — **no PUSH pattern found**.
