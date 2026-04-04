# CLIENT_AUTH_REQUEST

| Property | Value |
|----------|-------|
| Opcode | `0x6103` |
| Direction | Client → Server |
| Group | Client → Server |

### Fields

| # | Name | Type | Size | Description |
|---|------|------|------|-------------|
| 1 | `action` | `u8` | 1 |  |
| 2 | `result` | `u8` | 1 |  |
| 3 | `unk` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 4 | `ModelID` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 5 | `Name` | `string` | var | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 6 | `Scale` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 7 | `Level` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 8 | `Exp` | `u64` | 8 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 9 | `STR` | `u16` | 2 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 10 | `INT` | `u16` | 2 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 11 | `StatPoints` | `u16` | 2 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 12 | `HP` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 13 | `MP` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 14 | `isDeleting` | `bool` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) |
| 15 | `unk` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) |
| 16 | `GuildMemberType` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) |
| 17 | `isGuildRenameRequired` | `bool` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) |
| 18 | `GuildName` | `string` | var | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) |
| 19 | `AcademyMemberType` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) |
| 20 | `unk` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) |
| 21 | `unk` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) |
| 22 | `plus` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) |
| 23 | `unk` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) → if(inventory[j].isEquipable() |
| 24 | `unk` | `u32` | 4 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) → if(inventory[j].isEquipable() |
| 25 | `Plus` | `u8` | 1 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) → if(inventory[j].isEquipable() |
| 26 | `errCode` | `u16` | 2 | case(SRTypes.CharacterSelectionAction.Create) → if(result == 1) → if(Bot.Get.Proxy.ClientlessMode) → if(result == 1) → if(isDeleting) → if(isGuildRenameRequired) → if(inventory[j].isEquipable() |

