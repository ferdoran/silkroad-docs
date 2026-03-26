# Decompiled Handler Reference

All 295 unique message handler functions have been decompiled to C pseudocode using the r2ghidra decompiler. This page provides an overview of the decompilation results.

## Statistics

| Metric | Value |
|--------|-------|
| Total handlers decompiled | 295 |
| Total lines of C pseudocode | 26,328 |
| Handlers with conditional reads | 181 |
| Handlers with loop reads | 41 |
| Total Stream::Read calls found | 1,152 |
| Unique function calls identified | 869 |
| Shared functions (3+ handlers) | 121 |

## Key Functions Identified

### Message I/O

| Address | Function | Purpose |
|---------|----------|---------|
| `0x004F7220` | `Stream::Read` | Generic read: `Read(dest, size)` |
| `0x004B3B40` | `ReadByte` | Read 1 byte (u8) |
| `0x004D2820` | `ReadWord` | Read 2 bytes (u16) |
| `0x004B3BA0` | `ReadDword` | Read 4 bytes (u32) |
| `0x004B3C00` | `ReadQword` | Read 8 bytes (u64) |
| `0x004AF830` | `ReadBytes` | Read N bytes |
| `0x004EEA40` | `ReadFloat` | Read 4-byte float |
| `0x0053CEA0` | `CMsgStreamBuffer::Init` | Initialize outgoing message |
| `0x00508FE0` | `CMsgStreamBuffer::Write` | Write to outgoing message |
| `0x008418D0` | `CSession::Send` | Send message |
| `0x005097A0` | `CMsgStreamBuffer::Destroy` | Cleanup message buffer |

### Most-Called Shared Functions

| Address | Called By | Likely Purpose |
|---------|----------|----------------|
| `0x00778190` | 118 handlers | Show system message / notification |
| `0x00B42C6D` | 94 handlers | Stack security check (`__security_check_cookie`) |
| `0x008C9C30` | 72 handlers | UI string resource lookup |
| `0x007781B0` | 49 handlers | Display colored notification |
| `0x0046ED50` | 39 handlers | String operation (copy/set) |
| `0x00798D00` | 36 handlers | Entity manager operation |
| `0x004F7A70` | 32 handlers | Stream buffer operation |
| `0x009C3220` | 28 handlers | Entity lookup by unique ID |
| `0x0077B580` | 28 handlers | UI update / refresh |
| `0x0049D640` | 27 handlers | Debug logging |

### Assert Function

| Address | Function | Purpose |
|---------|----------|---------|
| `0x0049E490` | `Assert` | Debug assert with source file + expression |

Assert calls reveal original variable names and source files:
- `g_pMyPlayerObj->GetJobType() == byJobType`
- `!m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedSkill(dwSkillID)`
- `m_pGInterface->GetMainPopup()->GetSkillAddress()->GetLearnedSkill()->IsLearnedMastery(dwMasteryID)`

## Common Handler Patterns

### Result-Branching Pattern

Most client-response handlers follow this pattern:

```c
void handler(void) {
    Stream::Read(&byResult, 1);    // Read result byte

    if (byResult == 1) {
        // SUCCESS: read additional data fields
        Stream::Read(&dwData, 4);
        Stream::Read(&wParam, 2);
        // ... process data ...
        ShowMessage(L"UIIT_MSG_SUCCESS");
    }
    else if (byResult == 2) {
        // FAILURE: read error code
        Stream::Read(&wErrorCode, 2);
        ShowMessage(L"UIIT_MSG_FAIL");
    }
}
```

### Loop-Read Pattern

Used for variable-length lists (party members, guild members, items):

```c
Stream::Read(&byCount, 1);
for (int i = 0; i < byCount; i++) {
    Stream::Read(&dwMemberUID, 4);
    Stream::Read(&byLevel, 1);
    Stream::Read(&wHP, 2);
    // ... per-member data ...
}
```

### Type-Dispatch Pattern

Used for multi-purpose handlers:

```c
Stream::Read(&byType, 1);
switch (byType) {
    case 1:  // Type A
        Stream::Read(&fieldA, 4);
        break;
    case 2:  // Type B
        Stream::Read(&fieldB1, 4);
        Stream::Read(&fieldB2, 2);
        break;
}
```

## Source Files

The following original source files are referenced in assert strings:

| Source File | Handler Domain |
|-------------|----------------|
| `NetProcessInInterface.cpp` | UI/Interface message handling |
| `NetProcessInObject.cpp` | Game object updates |
| `NetProcessInInner.cpp` | Core/inner game logic |
| `NetProcessInNavAndSkill.cpp` | Navigation & skill processing |
| `IFMainPopup.cpp` | Main popup interface |
| `IFStall.cpp` | Stall/shop interface |
| `IF_NPCTalk.cpp` | NPC dialog interface |
| `NIFGuildWnd.cpp` | Guild window interface |
| `CharacterDependentData.cpp` | Character data management |
| `GlobalDataManager.cpp` | Global game data |
| `COSDataMgr.cpp` | COS (pet/transport) data |
| `IGIDObject.cpp` | GID object management |
