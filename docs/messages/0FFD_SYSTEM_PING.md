# SYSTEM_PING

| Property | Value |
|----------|-------|
| Opcode | `0x0FFD` |
| Direction | System (bidirectional keepalive) |
| Group | System/Debug |
| Handler(s) | `0x00888DA0` |

### Fields

**No payload.** This is a pure keepalive packet. The opcode `0x0FFD` does not appear
as a `PUSH` instruction in SR_GameServer.exe, GatewayServer.exe, AgentServer.exe,
or any of the SMPlugin DLLs, confirming it carries no payload by design.

The string reference `SMSG[0x%04X] %02d:%02d:%02d` in the client handler is debug
logging triggered on receipt — not a field read.

### Binary Evidence

Exhaustive search across all server binaries:

| Binary | PUSH 0x0FFD found | Result |
|--------|-------------------|--------|
| SR_GameServer.exe (clean) | No | No payload |
| GatewayServer.exe | No | No payload |
| AgentServer.exe | No | No payload |
| SR_ShardManager.exe | No | No payload |
| All SMPlugin DLLs | No | No payload |

### String References

| String | Type |
|--------|------|
| `SMSG[0x%04X] %02d:%02d:%02d` | Debug logging on receipt |
