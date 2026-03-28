# Silkroad Online Data Tables Reference

## Overview

- **Total tables**: 126
- **Total rows**: 156,114
- **Source format**: UTF-16LE with BOM, tab-separated

## Items

### collectionbook_item

- **Files**: collectionbook_item.txt
- **Rows**: 32
- **Columns**: 8

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `ITEM_TALISMAN_TOGUI_RED_TEARS`, `ITEM_TALISMAN_TOGUI_WESTERN_SCRIPTURES`, `ITEM_TALISMAN_TOGUI_TOGUI_MASK` |
| 2 | col_2 | string | `붉은 눈물`, `서역불경`, `토귀 가면` |
| 3 | col_3 | string | `THEME_GOD_TOGUI_RED_BLOOD`, `THEME_GOD_TOGUI_RED_BLOOD`, `THEME_GOD_TOGUI_RED_BLOOD` |
| 4 | col_4 | int | `1`, `1`, `1` |
| 5 | col_5 | int | `1`, `2`, `3` |
| 6 | col_6 | codename | `SN_ITEM_TALISMAN_TOGUI_RED_TEARS_TT_D...`, `SN_ITEM_TALISMAN_TOGUI_WESTERN_SCRIPT...`, `SN_ITEM_TALISMAN_TOGUI_TOGUI_MASK_TT_...` |
| 7 | col_7 | path (DDJ) | `icon\item\etc\talisman_togui_red_te.ddj`, `icon\item\etc\talisman_togui_western_...`, `icon\item\etc\talisman_togui_togui_m.ddj` |

### collectionbook_theme

- **Files**: collectionbook_theme.txt
- **Rows**: 4
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | string | `THEME_GOD_TOGUI_RED_BLOOD`, `THEME_GOD_FLAME_BURNING_ABYSS`, `THEME_GOD_WRECK_GREEN_DEEP_SEE` |
| 3 | col_3 | string | `토귀마을 - 붉은피의 환영`, `화염산 - 불타는 심연`, `난파선 - 초록빛 심해` |
| 4 | col_4 | codename | `SN_THEME_GOD_TOGUI_RED_BLOOD`, `SN_THEME_GOD_FLAME_BURNING_ABYSS`, `SN_THEME_GOD_WRECK_GREEN_DEEP_SEE` |
| 5 | col_5 | codename | `SN_THEME_GOD_TOGUI_RED_BLOOD_TT_DESC`, `SN_THEME_GOD_FLAME_BURNING_ABYSS_TT_DESC`, `SN_THEME_GOD_WRECK_GREEN_DEEP_SEE_TT_...` |
| 6 | col_6 | int | `8`, `8`, `8` |

### gachaitemset

- **Files**: gachaitemset.txt
- **Rows**: 3,345
- **Columns**: 16

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `1`, `1` |
| 2 | col_2 | int | `4014`, `4015`, `4016` |
| 3 | col_3 | int | `3000`, `3000`, `3000` |
| 4 | col_4 | int | `1`, `1`, `1` |
| 5 | col_5 | int | `1`, `2`, `3` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | int | `1`, `1`, `1` |
| 8 | col_8 | string | `[BIIV]<M:str,1,3><M:int,1,3><O:3>`, `[BIIV]<M:str,1,3><M:int,1,3><O:3>`, `[BIIV]<M:str,1,3><M:int,1,3><O:3>` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | int | `0`, `0`, `0` |
| 12 | col_12 | placeholder | `xxx`, `xxx`, `xxx` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | placeholder | `xxx`, `xxx`, `xxx` |
| 15 | col_15 | placeholder | ``, ``, `` |

### gachanpcmap

- **Files**: gachanpcmap.txt
- **Rows**: 1
- **Columns**: 4

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1` |
| 1 | col_1 | int | `9251` |
| 2 | col_2 | int | `1` |
| 3 | col_3 | int | `2` |

### item_grouping

- **Files**: item_grouping.txt
- **Rows**: 301
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `#section`, `//description`, `도복` |
| 1 | col_1 | codename | `GROUPING_TID`, `TID1`, `3` |
| 2 | col_2 | codename | ``, `TID2`, `1` |
| 3 | col_3 | string | ``, `TID3`, `1` |
| 4 | col_4 | string | ``, `TID4`, `1` |
| 5 | col_5 | codename | ``, `STRING`, `SN_ITEM_TOOLTIP_GROUPING_001` |
| 6 | col_6 | placeholder | ``, ``, `` |

### itemdata

- **Files**: itemdata_10000.txt, itemdata_15000.txt, itemdata_20000.txt, itemdata_25000.txt, itemdata_30000.txt, itemdata_35000.txt, itemdata_40000.txt, itemdata_45000.txt, itemdata_5000.txt
- **Rows**: 11,929
- **Columns**: 161

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `5000`, `5001`, `5002` |
| 2 | codename | codename | `ITEM_CH_W_HEAVY_05_HA_C_RARE`, `ITEM_CH_W_HEAVY_06_HA_A_RARE`, `ITEM_CH_W_HEAVY_06_HA_B_RARE` |
| 3 | korean_name | string | `5? ?? ?? [?] (?)`, `6? ?? ?? [?] (?)`, `6? ?? ?? [?] (?)` |
| 4 | xxx1 | codename | `ITEM_CH_M_HEAVY_05_HA_C_RARE`, `ITEM_CH_M_HEAVY_06_HA_A_RARE`, `ITEM_CH_M_HEAVY_06_HA_B_RARE` |
| 5 | name_ref | codename | `SN_ITEM_CH_HEAVY_05_HA_C_RARE`, `SN_ITEM_CH_HEAVY_06_HA_A_RARE`, `SN_ITEM_CH_HEAVY_06_HA_B_RARE` |
| 6 | desc_ref | codename | `SN_ITEM_CH_HEAVY_05_HA_C_RARE_TT_DESC`, `SN_ITEM_CH_HEAVY_06_HA_A_RARE_TT_DESC`, `SN_ITEM_CH_HEAVY_06_HA_B_RARE_TT_DESC` |
| 7 | xxx2 | int | `0`, `0`, `0` |
| 8 | xxx3 | int | `0`, `0`, `0` |
| 9 | xxx4 | int | `3`, `3`, `3` |
| 10 | tid2 | int | `1`, `1`, `1` |
| 11 | tid3 | int | `3`, `3`, `3` |
| 12 | tid4 | int | `1`, `1`, `1` |
| 13 | xxx5 | int | `180000`, `180000`, `180000` |
| 14 | xxx6 | int | `0`, `0`, `0` |
| 15 | xxx7 | int | `2`, `2`, `2` |
| 16 | xxx8 | int | `1`, `1`, `1` |
| 17 | xxx9 | int | `1`, `1`, `1` |
| 18 | xxx10 | int | `1`, `1`, `1` |
| 19 | xxx11 | int | `255`, `255`, `255` |
| 20 | xxx12 | int | `3`, `3`, `3` |
| 21 | xxx13 | int | `1`, `1`, `1` |
| 22 | xxx14 | int | `1`, `1`, `1` |
| 23 | xxx15 | int | `1`, `1`, `1` |
| 24 | xxx16 | int | `0`, `0`, `0` |
| 25 | xxx17 | int | `0`, `0`, `0` |
| 26 | xxx18 | int | `272000`, `272000`, `377500` |
| 27 | xxx19 | int | `1861`, `2074`, `2239` |
| 28 | xxx20 | int | `2792`, `3110`, `3358` |
| 29 | xxx21 | int | `0`, `0`, `0` |
| 30 | xxx22 | int | `2500`, `2500`, `6606` |
| 31 | xxx23 | int | `95200`, `95200`, `132125` |
| 32 | xxx24 | int | `1`, `1`, `1` |
| 33 | level | int | `35`, `45`, `45` |
| 34 | xxx25 | int | `-1`, `-1`, `-1` |
| 35 | xxx26 | int | `0`, `0`, `0` |
| 36 | xxx27 | int | `-1`, `-1`, `-1` |
| 37 | xxx28 | int | `0`, `0`, `0` |
| 38 | xxx29 | int | `-1`, `-1`, `-1` |
| 39 | xxx30 | int | `0`, `0`, `0` |
| 40 | xxx31 | int | `-1`, `-1`, `-1` |
| 41 | xxx32 | int | `0`, `0`, `0` |
| 42 | xxx33 | int | `0`, `0`, `0` |
| 43 | xxx34 | int | `0`, `0`, `0` |
| 44 | xxx35 | int | `0`, `0`, `0` |
| 45 | xxx36 | int | `0`, `0`, `0` |
| 46 | xxx37 | int | `0`, `0`, `0` |
| 47 | xxx38 | int | `0`, `0`, `0` |
| 48 | xxx39 | int | `100`, `100`, `100` |
| 49 | xxx40 | int | `0`, `0`, `0` |
| 50 | xxx41 | int | `0`, `0`, `0` |
| 51 | xxx42 | int | `0`, `0`, `0` |
| 52 | xxx43 | path (BSR) | `item\china\woman_item\heavy_05_ha.bsr`, `item\china\woman_item\heavy_06_ha.bsr`, `item\china\woman_item\heavy_06_ha.bsr` |
| 53 | xxx44 | path (BSR) | `item\etc\drop_ch_equip_rare.bsr`, `item\etc\drop_ch_equip_rare.bsr`, `item\etc\drop_ch_equip_rare.bsr` |
| 54 | icon | path (DDJ) | `item\china\woman_item\heavy_05_ha.ddj`, `item\china\woman_item\heavy_06_ha.ddj`, `item\china\woman_item\heavy_06_ha.ddj` |
| 55 | xxx45 | placeholder | `xxx`, `xxx`, `xxx` |
| 56 | xxx46 | placeholder | `xxx`, `xxx`, `xxx` |
| 57 | max_stack | int | `1`, `1`, `1` |
| 58 | col_58 | int | `0`, `0`, `0` |
| 59 | col_59 | int | `0`, `0`, `0` |
| 60 | col_60 | int | `0`, `0`, `0` |
| 61 | col_61 | int | `15`, `16`, `17` |
| 62 | col_62 | int | `0`, `0`, `0` |
| 63 | col_63 | int | `71`, `71`, `74` |
| 64 | col_64 | int | `87`, `87`, `90` |
| 65 | col_65 | float | `35.6`, `35.6`, `45.8` |
| 66 | col_66 | float | `43.5`, `43.5`, `49.2` |
| 67 | col_67 | float | `1.5`, `1.5`, `1.7` |
| 68 | col_68 | int | `19`, `19`, `22` |
| 69 | col_69 | int | `23`, `23`, `23` |
| 70 | col_70 | int | `0`, `0`, `0` |
| 71 | col_71 | int | `0`, `0`, `0` |
| 72 | col_72 | int | `0`, `0`, `0` |
| 73 | col_73 | int | `0`, `0`, `0` |
| 74 | col_74 | int | `0`, `0`, `0` |
| 75 | col_75 | int | `0`, `0`, `0` |
| 76 | col_76 | float | `46.6`, `46.6`, `60` |
| 77 | col_77 | float | `57`, `57`, `64.4` |
| 78 | col_78 | float | `2`, `2`, `2.3` |
| 79 | col_79 | int | `0`, `0`, `0` |
| 80 | col_80 | int | `0`, `0`, `0` |
| 81 | col_81 | int | `0`, `0`, `0` |
| 82 | col_82 | int | `104`, `104`, `125` |
| 83 | col_83 | int | `127`, `127`, `130` |
| 84 | col_84 | int | `136`, `136`, `164` |
| 85 | col_85 | int | `167`, `167`, `171` |
| 86 | col_86 | int | `0`, `0`, `0` |
| 87 | col_87 | int | `0`, `0`, `0` |
| 88 | col_88 | int | `0`, `0`, `0` |
| 89 | col_89 | int | `0`, `0`, `0` |
| 90 | col_90 | int | `0`, `0`, `0` |
| 91 | col_91 | int | `0`, `0`, `0` |
| 92 | col_92 | int | `0`, `0`, `0` |
| 93 | col_93 | int | `0`, `0`, `0` |
| 94 | col_94 | int | `0`, `0`, `0` |
| 95 | col_95 | int | `0`, `0`, `0` |
| 96 | col_96 | int | `0`, `0`, `0` |
| 97 | col_97 | int | `0`, `0`, `0` |
| 98 | col_98 | int | `0`, `0`, `0` |
| 99 | col_99 | int | `0`, `0`, `0` |
| 100 | col_100 | int | `0`, `0`, `0` |
| 101 | col_101 | int | `0`, `0`, `0` |
| 102 | col_102 | int | `0`, `0`, `0` |
| 103 | col_103 | int | `0`, `0`, `0` |
| 104 | col_104 | int | `0`, `0`, `0` |
| 105 | col_105 | int | `0`, `0`, `0` |
| 106 | col_106 | int | `0`, `0`, `0` |
| 107 | col_107 | int | `0`, `0`, `0` |
| 108 | col_108 | int | `0`, `0`, `0` |
| 109 | col_109 | int | `0`, `0`, `0` |
| 110 | col_110 | int | `0`, `0`, `0` |
| 111 | col_111 | int | `0`, `0`, `0` |
| 112 | col_112 | int | `0`, `0`, `0` |
| 113 | col_113 | int | `0`, `0`, `0` |
| 114 | col_114 | int | `0`, `0`, `0` |
| 115 | col_115 | int | `0`, `0`, `0` |
| 116 | col_116 | int | `0`, `0`, `0` |
| 117 | col_117 | int | `0`, `0`, `0` |
| 118 | col_118 | int | `-1`, `-1`, `-1` |
| 119 | col_119 | codename | `xxx`, `xxx`, `xxx` |
| 120 | col_120 | int | `-1`, `-1`, `-1` |
| 121 | col_121 | codename | `xxx`, `xxx`, `xxx` |
| 122 | col_122 | int | `-1`, `-1`, `-1` |
| 123 | col_123 | codename | `xxx`, `xxx`, `xxx` |
| 124 | col_124 | int | `-1`, `-1`, `-1` |
| 125 | col_125 | placeholder | `xxx`, `xxx`, `xxx` |
| 126 | col_126 | int | `-1`, `-1`, `-1` |
| 127 | col_127 | placeholder | `xxx`, `xxx`, `xxx` |
| 128 | col_128 | int | `-1`, `-1`, `-1` |
| 129 | col_129 | placeholder | `xxx`, `xxx`, `xxx` |
| 130 | col_130 | int | `-1`, `-1`, `-1` |
| 131 | col_131 | placeholder | `xxx`, `xxx`, `xxx` |
| 132 | col_132 | int | `-1`, `-1`, `-1` |
| 133 | col_133 | placeholder | `xxx`, `xxx`, `xxx` |
| 134 | col_134 | int | `-1`, `-1`, `-1` |
| 135 | col_135 | placeholder | `xxx`, `xxx`, `xxx` |
| 136 | col_136 | int | `-1`, `-1`, `-1` |
| 137 | col_137 | placeholder | `xxx`, `xxx`, `xxx` |
| 138 | col_138 | int | `-1`, `-1`, `-1` |
| 139 | col_139 | placeholder | `xxx`, `xxx`, `xxx` |
| 140 | col_140 | int | `-1`, `-1`, `-1` |
| 141 | col_141 | placeholder | `xxx`, `xxx`, `xxx` |
| 142 | col_142 | int | `-1`, `-1`, `-1` |
| 143 | col_143 | placeholder | `xxx`, `xxx`, `xxx` |
| 144 | col_144 | int | `-1`, `-1`, `-1` |
| 145 | col_145 | placeholder | `xxx`, `xxx`, `xxx` |
| 146 | col_146 | int | `-1`, `-1`, `-1` |
| 147 | col_147 | placeholder | `xxx`, `xxx`, `xxx` |
| 148 | col_148 | int | `-1`, `-1`, `-1` |
| 149 | col_149 | placeholder | `xxx`, `xxx`, `xxx` |
| 150 | col_150 | int | `-1`, `-1`, `-1` |
| 151 | col_151 | placeholder | `xxx`, `xxx`, `xxx` |
| 152 | col_152 | int | `-1`, `-1`, `-1` |
| 153 | col_153 | placeholder | `xxx`, `xxx`, `xxx` |
| 154 | col_154 | int | `-1`, `-1`, `-1` |
| 155 | col_155 | placeholder | `xxx`, `xxx`, `xxx` |
| 156 | col_156 | int | `0`, `0`, `0` |
| 157 | col_157 | string | `?? ??? ?? ?? ?`, `?? ??? ?? ?? ?`, `?? ??? ?? ?? ?` |
| 158 | col_158 | int | `9`, `9`, `9` |
| 159 | col_159 | int | `0`, `0`, `0` |
| 160 | col_160 | placeholder | ``, ``, `` |

## Characters & Monsters

### characterdata

- **Files**: characterdata_10000.txt, characterdata_15000.txt, characterdata_20000.txt, characterdata_25000.txt, characterdata_30000.txt, characterdata_35000.txt, characterdata_40000.txt, characterdata_45000.txt, characterdata_5000.txt
- **Rows**: 13,722
- **Columns**: 105

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `5850`, `5851`, `5852` |
| 2 | codename | codename | `MOB_EU_MOVOI_CLON`, `MOB_EU_MOVOI`, `MOB_EU_EDENP_CLON` |
| 3 | korean_name | string | `???`, `???`, `????` |
| 4 | xxx1 | codename | `MOB_EU_MOVOI`, `xxx`, `MOB_EU_EDENP` |
| 5 | name_ref | codename | `SN_MOB_EU_MOVOI_CLON`, `SN_MOB_EU_MOVOI`, `SN_MOB_EU_EDENP_CLON` |
| 6 | xxx2 | codename | `xxx`, `xxx`, `xxx` |
| 7 | xxx3 | int | `0`, `0`, `0` |
| 8 | xxx4 | int | `1`, `1`, `1` |
| 9 | xxx5 | int | `1`, `1`, `1` |
| 10 | tid2 | int | `2`, `2`, `2` |
| 11 | tid3 | int | `1`, `1`, `1` |
| 12 | tid4 | int | `1`, `1`, `1` |
| 13 | col_13 | int | `5000`, `5000`, `5000` |
| 14 | col_14 | int | `1`, `1`, `1` |
| 15 | col_15 | int | `0`, `0`, `0` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | int | `0`, `0`, `0` |
| 19 | col_19 | int | `0`, `0`, `0` |
| 20 | col_20 | int | `0`, `0`, `0` |
| 21 | col_21 | int | `0`, `0`, `0` |
| 22 | col_22 | int | `0`, `0`, `0` |
| 23 | col_23 | int | `0`, `0`, `0` |
| 24 | col_24 | int | `0`, `0`, `0` |
| 25 | col_25 | int | `0`, `0`, `0` |
| 26 | col_26 | int | `0`, `0`, `0` |
| 27 | col_27 | int | `0`, `0`, `0` |
| 28 | col_28 | int | `0`, `0`, `0` |
| 29 | col_29 | int | `0`, `0`, `0` |
| 30 | col_30 | int | `0`, `0`, `0` |
| 31 | col_31 | int | `0`, `0`, `0` |
| 32 | col_32 | int | `-1`, `-1`, `-1` |
| 33 | col_33 | int | `0`, `0`, `0` |
| 34 | col_34 | int | `-1`, `-1`, `-1` |
| 35 | col_35 | int | `0`, `0`, `0` |
| 36 | col_36 | int | `-1`, `-1`, `-1` |
| 37 | col_37 | int | `0`, `0`, `0` |
| 38 | col_38 | int | `-1`, `-1`, `-1` |
| 39 | col_39 | int | `0`, `0`, `0` |
| 40 | col_40 | int | `3`, `4`, `4` |
| 41 | col_41 | int | `0`, `0`, `0` |
| 42 | col_42 | int | `0`, `0`, `0` |
| 43 | col_43 | int | `0`, `0`, `0` |
| 44 | col_44 | int | `0`, `0`, `0` |
| 45 | col_45 | int | `0`, `0`, `0` |
| 46 | col_46 | int | `15`, `15`, `15` |
| 47 | col_47 | int | `45`, `45`, `40` |
| 48 | col_48 | int | `100`, `100`, `100` |
| 49 | col_49 | int | `0`, `0`, `0` |
| 50 | col_50 | int | `7`, `7`, `3` |
| 51 | col_51 | int | `0`, `0`, `0` |
| 52 | col_52 | path (BSR) | `xxx`, `mob\europe\movoi.bsr`, `xxx` |
| 53 | col_53 | placeholder | `xxx`, `xxx`, `xxx` |
| 54 | col_54 | path (DDJ) | `xxx`, `xxx`, `xxx` |
| 55 | col_55 | string | `xxx`, `xxx`, `xxx` |
| 56 | col_56 | placeholder | `xxx`, `xxx`, `xxx` |
| 57 | level | int | `1`, `2`, `3` |
| 58 | col_58 | int | `2`, `2`, `2` |
| 59 | hp | int | `54`, `55`, `85` |
| 60 | col_60 | int | `0`, `0`, `0` |
| 61 | col_61 | int | `0`, `0`, `0` |
| 62 | col_62 | int | `0`, `0`, `0` |
| 63 | col_63 | int | `0`, `0`, `0` |
| 64 | col_64 | int | `0`, `0`, `0` |
| 65 | col_65 | int | `0`, `0`, `0` |
| 66 | col_66 | int | `0`, `0`, `0` |
| 67 | col_67 | int | `0`, `0`, `0` |
| 68 | col_68 | int | `0`, `0`, `0` |
| 69 | col_69 | int | `0`, `0`, `0` |
| 70 | col_70 | int | `0`, `0`, `0` |
| 71 | col_71 | int | `9`, `9`, `9` |
| 72 | col_72 | int | `8`, `10`, `18` |
| 73 | col_73 | int | `1`, `2`, `3` |
| 74 | col_74 | int | `1`, `2`, `3` |
| 75 | col_75 | int | `27`, `29`, `31` |
| 76 | col_76 | int | `0`, `0`, `0` |
| 77 | col_77 | int | `27`, `29`, `31` |
| 78 | col_78 | int | `2`, `2`, `2` |
| 79 | col_79 | int | `24`, `47`, `71` |
| 80 | col_80 | int | `336860180`, `336860180`, `336860180` |
| 81 | col_81 | int | `3`, `3`, `3` |
| 82 | col_82 | int | `3000`, `3000`, `3000` |
| 83 | col_83 | int | `3598`, `3600`, `3602` |
| 84 | col_84 | int | `3599`, `3601`, `3603` |
| 85 | col_85 | int | `0`, `0`, `0` |
| 86 | col_86 | int | `0`, `0`, `0` |
| 87 | col_87 | int | `0`, `0`, `0` |
| 88 | col_88 | int | `0`, `0`, `0` |
| 89 | col_89 | int | `0`, `0`, `0` |
| 90 | col_90 | int | `0`, `0`, `0` |
| 91 | col_91 | int | `0`, `0`, `0` |
| 92 | col_92 | int | `0`, `0`, `0` |
| 93 | col_93 | int | `1`, `0`, `1` |
| 94 | col_94 | int | `0`, `0`, `0` |
| 95 | col_95 | int | `0`, `0`, `0` |
| 96 | col_96 | int | `0`, `0`, `0` |
| 97 | col_97 | int | `0`, `0`, `0` |
| 98 | col_98 | int | `0`, `0`, `0` |
| 99 | col_99 | int | `0`, `0`, `0` |
| 100 | col_100 | int | `0`, `0`, `0` |
| 101 | col_101 | int | `0`, `0`, `0` |
| 102 | col_102 | int | `0`, `0`, `0` |
| 103 | col_103 | int | `0`, `0`, `0` |
| 104 | col_104 | placeholder | ``, ``, `` |

### charactervisualchange

- **Files**: charactervisualchange.txt
- **Rows**: 181
- **Columns**: 21

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//Service`, `1`, `1` |
| 1 | col_1 | string | `ID`, `1`, `3` |
| 2 | col_2 | string | `Name`, `장비(ROBE-HELM)`, `장비(ROBE-SHOULDERGUARD)` |
| 3 | col_3 | string | `ConditionID`, `1`, `1` |
| 4 | col_4 | string | `AttachType`, `1`, `1` |
| 5 | col_5 | string | `Pram1`, `2220`, `4268` |
| 6 | col_6 | string | `Pram2`, `0`, `0` |
| 7 | col_7 | string | `Pram3`, `0`, `0` |
| 8 | col_8 | string | `Pram4`, `0`, `0` |
| 9 | col_9 | codename | `StrPram1`, `xxx`, `xxx` |
| 10 | col_10 | string | `StrPram2`, `xxx`, `xxx` |
| 11 | col_11 | string | `StrPram3`, `xxx`, `xxx` |
| 12 | col_12 | string | `StrPram4`, `xxx`, `xxx` |
| 13 | col_13 | string | `Slot`, `0x0801`, `0x0004` |
| 14 | col_14 | string | `OverlapSlot`, `0x0000`, `0x0000` |
| 15 | col_15 | string | `OverlapSlotGroup`, `0`, `0` |
| 16 | col_16 | string | `Priority`, `250`, `250` |
| 17 | col_17 | string | `MaterialID`, `0`, `0` |
| 18 | col_18 | string | `AnimationName`, `xxx`, `xxx` |
| 19 | col_19 | path (BSR) | `BsrName(M)`, `xxx`, `xxx` |
| 20 | col_20 | path (BSR) | `BsrName(F)`, `xxx`, `xxx` |

## Skills & Mastery

### erasablemastery

- **Files**: erasablemastery.txt
- **Rows**: 7
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1828`, `1828`, `1828` |
| 1 | col_1 | int | `257`, `258`, `259` |

### erasableskill

- **Files**: erasableskill.txt
- **Rows**: 205
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1828`, `1828`, `1828` |
| 1 | col_1 | int | `3`, `4`, `5` |

### skilldata

- **Files**: skilldata_10000.txt, skilldata_15000.txt, skilldata_20000.txt, skilldata_25000.txt, skilldata_30000.txt, skilldata_35000.txt, skilldata_5000.txt
- **Rows**: 31,407
- **Columns**: 119

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `5000`, `5001`, `5002` |
| 2 | group_id | int | `0`, `0`, `0` |
| 3 | basic_code | string | `HSKILL_SPEAR_PHYSICAL_0992`, `HSKILL_SWORD_MAGIC_0993`, `HSKILL_BOW_PHYSICAL_0994` |
| 4 | basic_name | string | `0992 ?? ??`, `0993 ?? ??`, `0994 ?? ??` |
| 5 | basic_group | placeholder | `xxx`, `xxx`, `xxx` |
| 6 | basic_original | int | `40`, `2`, `70` |
| 7 | basic_level | int | `100`, `100`, `100` |
| 8 | basic_activity | int | `2`, `2`, `2` |
| 9 | basic_chain_code | int | `0`, `0`, `0` |
| 10 | basic_recycle_cost | int | `0`, `0`, `0` |
| 11 | action_preparing_time | int | `0`, `0`, `0` |
| 12 | action_casting_time | int | `0`, `0`, `0` |
| 13 | action_duration | int | `1166`, `1200`, `840` |
| 14 | action_reuse_delay | int | `1749`, `1800`, `1260` |
| 15 | action_cool_time | int | `1749`, `1800`, `1260` |
| 16 | action_flying_speed | int | `0`, `0`, `400` |
| 17 | action_interruptable | int | `0`, `0`, `0` |
| 18 | action_overlap | int | `0`, `0`, `0` |
| 19 | action_auto_attack_type | int | `1`, `1`, `1` |
| 20 | action_in_town | int | `0`, `0`, `0` |
| 21 | action_range | int | `25`, `8`, `180` |
| 22 | target_required | int | `1`, `1`, `1` |
| 23 | target_type_animal | int | `1`, `1`, `1` |
| 24 | target_type_land | int | `0`, `0`, `0` |
| 25 | target_type_building | int | `0`, `0`, `0` |
| 26 | target_group_self | int | `0`, `0`, `0` |
| 27 | target_group_ally | int | `0`, `0`, `0` |
| 28 | target_group_party | int | `0`, `0`, `0` |
| 29 | target_group_enemy_m | int | `1`, `1`, `1` |
| 30 | target_group_enemy_p | int | `1`, `1`, `1` |
| 31 | target_group_neutral | int | `0`, `0`, `0` |
| 32 | target_group_dont_care | int | `0`, `0`, `0` |
| 33 | target_etc_select_dead | int | `0`, `0`, `0` |
| 34 | req_common_mastery1 | int | `0`, `0`, `0` |
| 35 | req_common_mastery2 | int | `0`, `0`, `0` |
| 36 | req_common_mastery_level1 | int | `0`, `0`, `0` |
| 37 | req_common_mastery_level2 | int | `0`, `0`, `0` |
| 38 | req_common_str | int | `0`, `0`, `0` |
| 39 | req_common_int | int | `0`, `0`, `0` |
| 40 | req_learn_skill1 | int | `0`, `0`, `0` |
| 41 | req_learn_skill2 | int | `0`, `0`, `0` |
| 42 | req_learn_skill3 | int | `0`, `0`, `0` |
| 43 | req_learn_skill_level1 | int | `0`, `0`, `0` |
| 44 | req_learn_skill_level2 | int | `0`, `0`, `0` |
| 45 | req_learn_skill_level3 | int | `0`, `0`, `0` |
| 46 | req_learn_sp | int | `0`, `0`, `0` |
| 47 | req_learn_race | int | `3`, `3`, `3` |
| 48 | req_restriction1 | int | `0`, `0`, `0` |
| 49 | req_restriction2 | int | `0`, `0`, `0` |
| 50 | req_cast_weapon1 | int | `4`, `2`, `6` |
| 51 | req_cast_weapon2 | int | `5`, `3`, `255` |
| 52 | consume_hp | int | `0`, `0`, `0` |
| 53 | consume_mp | int | `0`, `0`, `0` |
| 54 | consume_hp_ratio | int | `0`, `0`, `0` |
| 55 | consume_mp_ratio | int | `0`, `0`, `0` |
| 56 | consume_whan | int | `0`, `0`, `0` |
| 57 | ui_skill_tab | int | `255`, `255`, `255` |
| 58 | ui_skill_page | int | `255`, `255`, `255` |
| 59 | ui_skill_column | int | `255`, `255`, `255` |
| 60 | ui_skill_row | int | `255`, `255`, `255` |
| 61 | ui_icon_file | placeholder | `xxx`, `xxx`, `xxx` |
| 62 | ui_skill_name | placeholder | `xxx`, `xxx`, `xxx` |
| 63 | ui_skill_tooltip | placeholder | `xxx`, `xxx`, `xxx` |
| 64 | ui_skill_tooltip_desc | placeholder | `xxx`, `xxx`, `xxx` |
| 65 | ui_skill_study_desc | placeholder | `xxx`, `xxx`, `xxx` |
| 66 | ai_attack_chance | int | `80`, `80`, `80` |
| 67 | ai_skill_type | int | `80`, `80`, `80` |
| 68 | param1 | int | `0`, `0`, `1` |
| 69 | param2 | int | `6386804`, `6386804`, `6386804` |
| 70 | param3 | int | `5`, `9`, `6` |
| 71 | param4 | int | `106`, `55`, `76` |
| 72 | param5 | int | `6091`, `8763`, `6091` |
| 73 | param6 | int | `7023`, `9695`, `7023` |
| 74 | param7 | int | `0`, `0`, `0` |
| 75 | param8 | int | `28003`, `28003`, `28003` |
| 76 | param9 | int | `2`, `2`, `2` |
| 77 | param10 | int | `1`, `2`, `1` |
| 78 | param11 | int | `0`, `0`, `0` |
| 79 | param12 | int | `0`, `26234`, `0` |
| 80 | param13 | int | `0`, `220`, `0` |
| 81 | param14 | int | `0`, `5`, `0` |
| 82 | param15 | int | `0`, `26210`, `0` |
| 83 | param16 | int | `0`, `220`, `0` |
| 84 | param17 | int | `0`, `25`, `0` |
| 85 | param18 | int | `0`, `0`, `0` |
| 86 | param19 | int | `0`, `0`, `0` |
| 87 | param20 | int | `0`, `0`, `0` |
| 88 | param21 | int | `0`, `0`, `0` |
| 89 | param22 | int | `0`, `0`, `0` |
| 90 | param23 | int | `0`, `0`, `0` |
| 91 | param24 | int | `0`, `0`, `0` |
| 92 | param25 | int | `0`, `0`, `0` |
| 93 | param26 | int | `0`, `0`, `0` |
| 94 | param27 | int | `0`, `0`, `0` |
| 95 | param28 | int | `0`, `0`, `0` |
| 96 | param29 | int | `0`, `0`, `0` |
| 97 | param30 | int | `0`, `0`, `0` |
| 98 | param31 | int | `0`, `0`, `0` |
| 99 | param32 | int | `0`, `0`, `0` |
| 100 | param33 | int | `0`, `0`, `0` |
| 101 | param34 | int | `0`, `0`, `0` |
| 102 | param35 | int | `0`, `0`, `0` |
| 103 | param36 | int | `0`, `0`, `0` |
| 104 | param37 | int | `0`, `0`, `0` |
| 105 | param38 | int | `0`, `0`, `0` |
| 106 | param39 | int | `0`, `0`, `0` |
| 107 | param40 | int | `0`, `0`, `0` |
| 108 | param41 | int | `0`, `0`, `0` |
| 109 | param42 | int | `0`, `0`, `0` |
| 110 | param43 | int | `0`, `0`, `0` |
| 111 | param44 | int | `0`, `0`, `0` |
| 112 | param45 | int | `0`, `0`, `0` |
| 113 | param46 | int | `0`, `0`, `0` |
| 114 | param47 | int | `0`, `0`, `0` |
| 115 | param48 | int | `0`, `0`, `0` |
| 116 | param49 | int | `0`, `0`, `0` |
| 117 | param50 | int | `0`, `0`, `0` |
| 118 | col_118 | placeholder | ``, ``, `` |

## Quests

### questdata

- **Files**: questdata.txt
- **Rows**: 713
- **Columns**: 12

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `27`, `28`, `29` |
| 2 | codename | codename | `QNO_KT_SMITH_1`, `QNO_WC_PRIEST1_1`, `QSP_ALL_POTION_1` |
| 3 | npc_id | int | `59`, `21`, `20` |
| 4 | korean_name | string | `<????>???? ??`, `<??>??? ??`, `??? ?? ???` |
| 5 | name_ref | codename | `SN_QNO_KT_SMITH_1`, `SN_QNO_WC_PRIEST1_1`, `SN_QSP_ALL_POTION_1` |
| 6 | reward_ref | codename | `SN_PAY_QNO_KT_SMITH_1`, `SN_PAY_QNO_WC_PRIEST1_1`, `SN_PAY_QSP_ALL_POTION_1` |
| 7 | xxx1 | placeholder | `xxx`, `xxx`, `xxx` |
| 8 | xxx2 | codename | `SN_PAYCON_QNO_KT_SMITH_1`, `SN_PAYCON_QNO_WC_PRIEST1_1`, `SN_PAYCON_QSP_ALL_POTION_1` |
| 9 | xxx3 | codename | `SN_NN_QNO_KT_SMITH_1`, `SN_NN_QNO_WC_PRIEST1_1`, `SN_NN_QSP_ALL_POTION_1` |
| 10 | xxx4 | codename | `SN_NC_QNO_KT_SMITH_1`, `SN_NC_QNO_WC_PRIEST1_1`, `SN_NC_QSP_ALL_POTION_1` |
| 11 | xxx5 | placeholder | ``, ``, `` |

## Shops

### shopdata

- **Files**: shopdata.txt
- **Rows**: 57
- **Columns**: 18

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `1`, `2`, `3` |
| 2 | codename | codename | `MALL_CONSUME`, `STORE_CH_SMITH`, `STORE_CH_ARMOR` |
| 3 | korean_name | placeholder | `xxx`, `xxx`, `xxx` |
| 4 | xxx1 | int | `0`, `0`, `0` |
| 5 | xxx2 | int | `-268435455`, `2003`, `2004` |
| 6 | tab1 | int | `642`, `579`, `582` |
| 7 | tab2 | int | `643`, `580`, `583` |
| 8 | tab3 | int | `644`, `581`, `584` |
| 9 | tab4 | int | `645`, `0`, `585` |
| 10 | tab5 | int | `646`, `0`, `586` |
| 11 | tab6 | int | `0`, `0`, `587` |
| 12 | tab7 | int | `0`, `0`, `0` |
| 13 | tab8 | int | `0`, `0`, `0` |
| 14 | tab9 | int | `0`, `0`, `0` |
| 15 | tab10 | int | `0`, `0`, `0` |
| 16 | tab11 | placeholder | `xxx`, `xxx`, `xxx` |
| 17 | tab12 | placeholder | `xxx`, `xxx`, `xxx` |

## Teleport

### teleportdata

- **Files**: teleportdata.txt
- **Rows**: 200
- **Columns**: 14

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | path | `1`, `1`, `1` |
| 1 | id | int | `1`, `2`, `3` |
| 2 | codename | codename | `GATE_CH                              ...`, `GATE_WC                              ...`, `GATE_NPC_CH_FERRY                    ...` |
| 3 | npc_id | int | `2094`, `2095`, `2011` |
| 4 | name_ref | codename | `SN_ZONE_22001`, `SN_ZONE_22002`, `SN_ZONE_21002` |
| 5 | zone_id | int | `25000`, `26265`, `24993` |
| 6 | region_id | int | `969`, `957`, `560` |
| 7 | pos_x | int | `0`, `-80`, `140` |
| 8 | pos_y | int | `1369`, `1508`, `1460` |
| 9 | pos_z | int | `150`, `200`, `200` |
| 10 | xxx1 | int | `1`, `1`, `0` |
| 11 | xxx2 | int | `0`, `0`, `0` |
| 12 | xxx3 | int | `1`, `1`, `1` |
| 13 | xxx4 | placeholder | ``, ``, `` |

### teleportlink

- **Files**: teleportlink.txt
- **Rows**: 239
- **Columns**: 23

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | src_id | int | `1`, `1`, `1` |
| 2 | dst_id | int | `2`, `175`, `176` |
| 3 | cost | int | `5000`, `40000`, `40000` |
| 4 | xxx1 | int | `0`, `0`, `0` |
| 5 | xxx2 | int | `0`, `0`, `0` |
| 6 | xxx3 | int | `0`, `0`, `0` |
| 7 | xxx4 | int | `2`, `1`, `1` |
| 8 | level_min | int | `0`, `95`, `95` |
| 9 | level_max | int | `0`, `999`, `999` |
| 10 | xxx5 | int | `0`, `2`, `2` |
| 11 | xxx6 | int | `0`, `0`, `0` |
| 12 | xxx7 | int | `0`, `0`, `0` |
| 13 | xxx8 | int | `0`, `0`, `0` |
| 14 | xxx9 | int | `0`, `0`, `0` |
| 15 | xxx10 | int | `0`, `0`, `0` |
| 16 | xxx11 | int | `0`, `0`, `0` |
| 17 | xxx12 | int | `0`, `0`, `0` |
| 18 | xxx13 | int | `0`, `0`, `0` |
| 19 | xxx14 | int | `0`, `0`, `0` |
| 20 | xxx15 | int | `0`, `0`, `0` |
| 21 | xxx16 | int | `0`, `0`, `0` |
| 22 | xxx17 | placeholder | ``, ``, `` |

## Levels

### hwanleveldata

- **Files**: hwanleveldata.txt
- **Rows**: 7
- **Columns**: 3

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `0`, `1`, `2` |
| 1 | col_1 | string | `xxx`, `UIO_SECOND_HWAN_CH_NAME_LEVEL_1`, `UIO_SECOND_HWAN_CH_NAME_LEVEL_2` |
| 2 | col_2 | string | `xxx`, `UIO_SECOND_HWAN_EU_NAME_LEVEL_1`, `UIO_SECOND_HWAN_EU_NAME_LEVEL_2` |

### leveldata

- **Files**: leveldata.txt
- **Rows**: 140
- **Columns**: 9

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `2`, `3` |
| 1 | xxx1 | int | `118`, `470`, `1058` |
| 2 | level | int | `1`, `1`, `1` |
| 3 | mob_exp | int | `0`, `0`, `0` |
| 4 | player_exp | int | `0`, `0`, `0` |
| 5 | xxx2 | int | `24`, `47`, `71` |
| 6 | total_exp | int | `70875`, `2388750`, `8793750` |
| 7 | total_exp2 | int | `70875`, `2388750`, `8793750` |
| 8 | xxx3 | int | `70875`, `2388750`, `8793750` |

## Magic Options

### magicoption

- **Files**: magicoption.txt
- **Rows**: 391
- **Columns**: 49

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | service | int | `1`, `1`, `1` |
| 1 | id | int | `1`, `2`, `3` |
| 2 | codename | codename | `MATTR_DEC_MAXDUR`, `MATTR_DEC_MAXDUR`, `MATTR_DEC_MAXDUR` |
| 3 | sign | string | `-@`, `-@`, `-@` |
| 4 | degree | int | `1`, `2`, `3` |
| 5 | value | float | `0.5`, `0.25`, `0.125` |
| 6 | xxx1 | int | `0`, `0`, `0` |
| 7 | xxx2 | int | `1685418593`, `1685418593`, `1685418593` |
| 8 | xxx3 | int | `7`, `7`, `7` |
| 9 | xxx4 | int | `5`, `21`, `36` |
| 10 | max_value | int | `20`, `35`, `50` |
| 11 | col_11 | int | `1949133172`, `1949133172`, `1949133172` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `0`, `0`, `0` |
| 15 | col_15 | int | `0`, `0`, `0` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | int | `0`, `0`, `0` |
| 19 | col_19 | int | `0`, `0`, `0` |
| 20 | col_20 | int | `0`, `0`, `0` |
| 21 | col_21 | int | `0`, `0`, `0` |
| 22 | col_22 | int | `0`, `0`, `0` |
| 23 | col_23 | int | `1685418593`, `1685418593`, `1685418593` |
| 24 | col_24 | int | `0`, `0`, `0` |
| 25 | col_25 | int | `0`, `0`, `0` |
| 26 | col_26 | int | `0`, `0`, `0` |
| 27 | col_27 | int | `0`, `0`, `0` |
| 28 | col_28 | int | `0`, `0`, `0` |
| 29 | col_29 | string | `weapon`, `weapon`, `weapon` |
| 30 | col_30 | int | `1`, `1`, `1` |
| 31 | col_31 | string | `armor`, `armor`, `armor` |
| 32 | col_32 | int | `1`, `1`, `1` |
| 33 | col_33 | string | `shield`, `shield`, `shield` |
| 34 | col_34 | int | `1`, `1`, `1` |
| 35 | col_35 | string | `xxx`, `xxx`, `xxx` |
| 36 | col_36 | int | `0`, `0`, `0` |
| 37 | col_37 | placeholder | `xxx`, `xxx`, `xxx` |
| 38 | col_38 | int | `0`, `0`, `0` |
| 39 | col_39 | placeholder | `xxx`, `xxx`, `xxx` |
| 40 | col_40 | int | `0`, `0`, `0` |
| 41 | col_41 | placeholder | `xxx`, `xxx`, `xxx` |
| 42 | col_42 | int | `0`, `0`, `0` |
| 43 | col_43 | placeholder | `xxx`, `xxx`, `xxx` |
| 44 | col_44 | int | `0`, `0`, `0` |
| 45 | col_45 | placeholder | `xxx`, `xxx`, `xxx` |
| 46 | col_46 | int | `0`, `0`, `0` |
| 47 | col_47 | placeholder | `xxx`, `xxx`, `xxx` |
| 48 | col_48 | int | `0`, `0`, `0` |

## Regions & Maps

### gameworldconfigdata

- **Files**: gameworldconfigdata.txt
- **Rows**: 825
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `GROUP_ARENA_FLAG_16_GATE`, `GROUP_ARENA_FLAG_16_GATE`, `GROUP_ARENA_FLAG_16_GATE` |
| 1 | col_1 | string | `REF_TELEPORT_BATTLE_ARENA_A_GATE`, `REF_TELEPORT_BATTLE_ARENA_B_GATE`, `BATTLE_ARENA_REWARD_WIN` |
| 2 | col_2 | string | `STRING`, `STRING`, `FLOAT32` |
| 3 | col_3 | codename | `GATE_ARENA_FLAG_16_A_GATE`, `GATE_ARENA_FLAG_16_B_GATE`, `25` |
| 4 | col_4 | placeholder | ``, ``, `` |

### gameworlddata

- **Files**: gameworlddata.txt
- **Rows**: 95
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `2`, `3` |
| 1 | col_1 | string | `INS_DEFAULT`, `INS_FORT_JA`, `INS_FORT_DW` |
| 2 | col_2 | int | `0`, `0`, `0` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `0`, `300`, `300` |
| 5 | col_5 | string | `xxx`, `GROUP_FORTRESS_JANGAN`, `GROUP_FORTRESS_DONWHANG` |
| 6 | col_6 | placeholder | ``, ``, `` |

### npcpos

- **Files**: npcpos.txt
- **Rows**: 12,367
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | region_id | int | `2023`, `2030`, `2034` |
| 1 | npc_id | int | `25257`, `25257`, `25001` |
| 2 | pos_x | float | `659.73999`, `692.15997`, `1387.17` |
| 3 | pos_y | float | `0.0`, `-0.02`, `-0.07` |
| 4 | pos_z | float | `981.13`, `137.35001`, `1765.02` |

### refregion

- **Files**: refregion.txt
- **Rows**: 2,462
- **Columns**: 21

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | region_id | int | `-32767`, `-32766`, `-32765` |
| 1 | xxx1 | int | `0`, `0`, `0` |
| 2 | xxx2 | int | `0`, `0`, `0` |
| 3 | codename | codename | `West_China`, `TQ`, `TQ` |
| 4 | korean_name | string | `???? ??`, `???? ??6?`, `???? ??5?` |
| 5 | is_dungeon | int | `1`, `1`, `1` |
| 6 | area_id | int | `1005`, `1001`, `1001` |
| 7 | xxx3 | int | `-1`, `-1`, `-1` |
| 8 | xxx4 | int | `0`, `0`, `0` |
| 9 | xxx5 | int | `0`, `0`, `0` |
| 10 | xxx6 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | xxx7 | string | `NULL`, `NULL`, `NULL` |
| 12 | xxx8 | string | `NULL`, `NULL`, `NULL` |
| 13 | xxx9 | string | `NULL`, `NULL`, `NULL` |
| 14 | xxx10 | string | `NULL`, `NULL`, `NULL` |
| 15 | xxx11 | string | `NULL`, `NULL`, `NULL` |
| 16 | xxx12 | string | `NULL`, `NULL`, `NULL` |
| 17 | xxx13 | string | `NULL`, `NULL`, `NULL` |
| 18 | xxx14 | string | `NULL`, `NULL`, `NULL` |
| 19 | xxx15 | string | `NULL`, `NULL`, `NULL` |
| 20 | xxx16 | string | `NULL`, `NULL`, `NULL` |

## Effects & Visuals

### actionwnddata

- **Files**: actionwnddata.txt
- **Rows**: 26
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1000`, `1001`, `1002` |
| 1 | col_1 | int | `1`, `1`, `1` |
| 2 | col_2 | string | `앉기서기`, `걷기뛰기`, `자동공격` |
| 3 | col_3 | string | `UIIT_CTL_TOG_SIT_STAND_TT`, `UIIT_CTL_TOG_RUN_WALK_TT`, `UIIT_CTL_AUTOATTACK_TT` |
| 4 | col_4 | path (DDJ) | `icon\action\icon_cha_sit.ddj`, `icon\action\icon_cha_walk.ddj`, `icon\action\icon_cha_auto_attack.ddj` |
| 5 | col_5 | int | `1`, `1`, `1` |
| 6 | col_6 | int | `0`, `1`, `2` |

### atstructeffect

- **Files**: atstructeffect.txt
- **Rows**: 1,023
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//유니코드로 저장!!!     경로는 소문자!!!`, `downgrade=1`, `upgrade=2` |
| 1 | col_1 | string | ``, ``, `` |
| 2 | col_2 | path (BSR, EFP) | ``, ``, `` |
| 3 | col_3 | string | ``, ``, `` |
| 4 | col_4 | float | ``, ``, `` |
| 5 | col_5 | float | ``, ``, `` |
| 6 | col_6 | string | ``, ``, `` |
| 7 | col_7 | string | ``, ``, `` |
| 8 | col_8 | string | `always=0`, ``, `` |
| 9 | col_9 | placeholder | ``, ``, `` |

### effectenvsnd

- **Files**: effectenvsnd.txt
- **Rows**: 1
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `ㄼा떵﯀뚸므उउ਍∉慅瑳牥䕮牵灯彥楆汥⹤杯≧उउ਍㰉㸲댉ষउ਍उ㰉㸳∉楮桧...` |

### effectsound

- **Files**: effectsound.txt
- **Rows**: 96
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `⼯漉橢捥ॴ慨摮敬猉楫汬䥟ॄ癥湥ㅴ攉敶瑮ल癥湥㍴戉慬歮昉汯敤ॲ楦敬慮敭瘉汯浵...`, `뷀ഉऊ呉䵅匉䑎䕟啑偉ⴉ䌉䥕卓ॅभभर極ड़瑩畃獩敳眮癡㠉र쿇ꦰ뀨뾩⧊쀠싥...`, `뷀ഉऊ呉䵅匉䑎䕟啑偉ⴉ䜉䕒噁ॅभभर極ड़瑩片慥敶眮癡㠉र얽�뀨뾩⧊쀠싥...` |

## Events

### eventdata

- **Files**: eventdata.txt
- **Rows**: 0
- **Columns**: 0

### eventguidedata

- **Files**: eventguidedata.txt
- **Rows**: 56
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | string | `레벨 도달`, `레벨 도달`, `레벨 도달` |
| 2 | col_2 | string | `xxx`, `xxx`, `xxx` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | codename | `2`, `5`, `19` |
| 5 | col_5 | int | `0`, `0`, `0` |
| 6 | col_6 | int | `50008`, `50010`, `50012` |

### eventword

- **Files**: eventword.txt
- **Rows**: 2
- **Columns**: 3

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `2` |
| 1 | col_1 | codename | `ITEM_ETC_E100630_VIETNAM_2`, `ITEM_ETC_E100630_VIETNAM_9` |
| 2 | col_2 | int | `2`, `9` |

### eventzonedata

- **Files**: eventzonedata.txt
- **Rows**: 286
- **Columns**: 14

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | codename | `GATE_DUNGEON_DH_IN`, `GATE_DUNGEON_DH_OUT`, `GATE_JINSI_OUT` |
| 3 | col_3 | codename | `TELEPORT`, `TELEPORT`, `TELEPORT` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | int | `0`, `0`, `0` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | codename | `GATE_DUNGEON_DH_IN`, `GATE_DUNGEON_DH_OUT`, `GATE_JINSI_OUT` |
| 10 | col_10 | string | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | placeholder | `xxx`, `xxx`, `xxx` |
| 12 | col_12 | placeholder | `xxx`, `xxx`, `xxx` |
| 13 | col_13 | placeholder | `xxx`, `xxx`, `xxx` |

## Dungeons

### dungeoninfo

- **Files**: dungeoninfo.txt
- **Rows**: 1
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `⼯렠솮䦯ॄ쓆쿀쳀Ꞹ਍ऱ䐢湵敧湯睜档湩屡畄桮慷杮䍟⹶潤≦਍ल䐢湵敧湯捜楨慮橜...` |

## Misc

### aaa

- **Files**: aaa.txt
- **Rows**: 3
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `PARAM_MASTERY_WEAPON_ATT_INCREASE`, `装备时提高攻击力%d %% `, `装备时提高攻击力%d %% ` |
| 1 | col_1 | string | `장착시 공격력 %d %% 증가`, ``, `` |

### abusefilter

- **Files**: AbuseFilter.txt
- **Rows**: 216
- **Columns**: 36

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 1 | col_1 | string | `0x0030`, `0x0041`, `0x005F` |
| 2 | col_2 | string | `0x0039`, `0x005A`, `0x005F` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 7 | col_7 | string | `0x0030`, `0x0041`, `0x0061` |
| 8 | col_8 | string | `0x0039`, `0x005A`, `0x007A` |
| 9 | col_9 | placeholder | ``, ``, `` |
| 10 | col_10 | placeholder | ``, ``, `` |
| 11 | col_11 | placeholder | ``, ``, `` |
| 12 | col_12 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 13 | col_13 | string | `0x0030`, `0x0041`, `0x0061` |
| 14 | col_14 | string | `0x0039`, `0x005A`, `0x007A` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |
| 18 | col_18 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 19 | col_19 | string | `0x0028`, `0x002B`, `0x002D` |
| 20 | col_20 | string | `0x0029`, `0x002B`, `0x002D` |
| 21 | col_21 | placeholder | ``, ``, `` |
| 22 | col_22 | placeholder | ``, ``, `` |
| 23 | col_23 | placeholder | ``, ``, `` |
| 24 | col_24 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 25 | col_25 | string | `0x0030`, `0x0041`, `0x005F` |
| 26 | col_26 | string | `0x0039`, `0x005A`, `0x005F` |
| 27 | col_27 | placeholder | ``, ``, `` |
| 28 | col_28 | placeholder | ``, ``, `` |
| 29 | col_29 | placeholder | ``, ``, `` |
| 30 | col_30 | string | `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE`, `#ALLOW_ID_TABLE` |
| 31 | col_31 | string | `0x0030`, `0x0041`, `0x005F` |
| 32 | col_32 | string | `0x0039`, `0x005A`, `0x005F` |
| 33 | col_33 | placeholder | ``, ``, `` |
| 34 | col_34 | placeholder | ``, ``, `` |
| 35 | col_35 | placeholder | ``, ``, `` |

### dg

- **Files**: dg.txt
- **Rows**: 140
- **Columns**: 3

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `2`, `3` |
| 1 | col_1 | int | `28`, `32`, `35` |
| 2 | col_2 | int | `42`, `47`, `53` |

### fmncategorytreedata

- **Files**: fmncategorytreedata.txt
- **Rows**: 72
- **Columns**: 6

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | string | `WK_CH_WEAPON`, `WK_CH_WEAPON_SWORD`, `WK_CH_WEAPON_BLADE` |
| 2 | col_2 | string | `UIIT_CTL_WK_CH_WEAPON`, `UIIT_CTL_WK_CH_WEAPON_SWORD`, `UIIT_CTL_WK_CH_WEAPON_BLADE` |
| 3 | col_3 | string | `xxx`, `WK_CH_WEAPON`, `WK_CH_WEAPON` |
| 4 | col_4 | int | `0`, `1`, `2` |
| 5 | col_5 | int | `0`, `11`, `11` |

### fmntidgroupmapdata

- **Files**: fmntidgroupmapdata.txt
- **Rows**: 138
- **Columns**: 6

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | int | `3`, `3`, `3` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `6`, `6`, `6` |
| 5 | col_5 | int | `2`, `3`, `4` |

### force_addobject

- **Files**: force_addobject.txt
- **Rows**: 54
- **Columns**: 12

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//반드시 유니코드로 저장`, `//서비스`, `1` |
| 1 | col_1 | path (BSR) | ``, `BSR경로`, `res\artifact\guild\flag\fortress_flag...` |
| 2 | col_2 | path | `//요새전 승리길드 표시 깃발 좌표`, `리전X`, `71` |
| 3 | col_3 | string | ``, `리전Y`, `68` |
| 4 | col_4 | string | ``, `X 좌표`, `691` |
| 5 | col_5 | string | ``, `Y 좌표`, `133` |
| 6 | col_6 | string | ``, `Z 좌표`, `1907` |
| 7 | col_7 | string | ``, `회전값`, `0` |
| 8 | col_8 | string | ``, `Type(깃발0, 구조물1)`, `0` |
| 9 | col_9 | path | ``, `길드0/동맹1`, `0` |
| 10 | col_10 | string | ``, `요새ID(siegefortreess.txt참조)`, `FORTRESS_JANGAN` |
| 11 | col_11 | path | ``, ``, `// 장안요새남문 좌` |

### gameguidedata

- **Files**: gameguidedata.txt
- **Rows**: 1,023
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1000`, `1001`, `1002` |
| 2 | col_2 | path | `플레이가이드`, `성장하는 법`, `스탯포인트` |
| 3 | col_3 | int | `0`, `1`, `1` |
| 4 | col_4 | int | `5`, `1000`, `1000` |
| 5 | col_5 | codename | `SRO_GGW_PG_MSG`, `SRO_GGW_PG_GROWTH`, `SRO_GGW_PG_STATP` |
| 6 | col_6 | codename | `SRO_GGW_MENU_PG_MSG`, `SRO_GGW_MENU_PG_GROWTH`, `SRO_GGW_MENU_PG_STATP` |

### groupworld_config_forclient

- **Files**: groupworld_config_forclient.txt
- **Rows**: 4
- **Columns**: 3

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | string | `TIMEDJOB_COOL_TIME_FORCLIENT`, `TIMEDJOB_ICONURL_FORCLIENT`, `TIMEDJOB_EXPANATION_FORCLIENT` |
| 2 | col_2 | path (DDJ) | `300`, `icon\item\etc\teleprot_hole.ddj`, `UIIT_STT_PARTY_LOST_WOLRD_EXPANATION` |

### itemeffect

- **Files**: itemeffect.txt
- **Rows**: 46
- **Columns**: 4

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//아이템 연출 문서`, `#section`, `//SkillEffect Codename` |
| 1 | col_1 | codename | ``, `itemcodename`, `SkillEffect Codename` |
| 2 | col_2 | string | ``, ``, `상태` |
| 3 | col_3 | string | ``, ``, `` |

### learnablemastery

- **Files**: learnablemastery.txt
- **Rows**: 14
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1831`, `1831`, `1832` |
| 1 | col_1 | int | `257`, `274`, `258` |

### learnableskill

- **Files**: learnableskill.txt
- **Rows**: 205
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1831`, `1831`, `1831` |
| 1 | col_1 | int | `3`, `4`, `5` |

### levelgold

- **Files**: levelgold.txt
- **Rows**: 140
- **Columns**: 3

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `2`, `3` |
| 1 | col_1 | int | `28`, `32`, `35` |
| 2 | col_2 | int | `59`, `66`, `74` |

### magicoptionassign

- **Files**: magicoptionassign.txt
- **Rows**: 74
- **Columns**: 29

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `0`, `0`, `0` |
| 2 | col_2 | int | `6`, `6`, `6` |
| 3 | col_3 | int | `2`, `3`, `4` |
| 4 | col_4 | codename | `MATTR_STR`, `MATTR_STR`, `MATTR_STR` |
| 5 | col_5 | codename | `MATTR_INT`, `MATTR_INT`, `MATTR_INT` |
| 6 | col_6 | codename | `MATTR_ATHANASIA`, `MATTR_ATHANASIA`, `MATTR_ATHANASIA` |
| 7 | col_7 | codename | `MATTR_SOLID`, `MATTR_SOLID`, `MATTR_SOLID` |
| 8 | col_8 | codename | `MATTR_LUCK`, `MATTR_LUCK`, `MATTR_LUCK` |
| 9 | col_9 | codename | `MATTR_DUR`, `MATTR_DUR`, `MATTR_DUR` |
| 10 | col_10 | codename | `MATTR_HR`, `MATTR_HR`, `MATTR_HR` |
| 11 | col_11 | codename | `MATTR_EVADE_BLOCK`, `MATTR_EVADE_BLOCK`, `MATTR_EVADE_BLOCK` |
| 12 | col_12 | codename | `MATTR_REPAIR`, `MATTR_REPAIR`, `MATTR_REPAIR` |
| 13 | col_13 | codename | `xxx`, `xxx`, `xxx` |
| 14 | col_14 | codename | `xxx`, `xxx`, `xxx` |
| 15 | col_15 | codename | `xxx`, `xxx`, `xxx` |
| 16 | col_16 | codename | `xxx`, `xxx`, `xxx` |
| 17 | col_17 | codename | `xxx`, `xxx`, `xxx` |
| 18 | col_18 | codename | `xxx`, `xxx`, `xxx` |
| 19 | col_19 | codename | `xxx`, `xxx`, `xxx` |
| 20 | col_20 | codename | `xxx`, `xxx`, `xxx` |
| 21 | col_21 | codename | `xxx`, `xxx`, `xxx` |
| 22 | col_22 | codename | `xxx`, `xxx`, `xxx` |
| 23 | col_23 | codename | `xxx`, `xxx`, `xxx` |
| 24 | col_24 | placeholder | `xxx`, `xxx`, `xxx` |
| 25 | col_25 | placeholder | `xxx`, `xxx`, `xxx` |
| 26 | col_26 | placeholder | `xxx`, `xxx`, `xxx` |
| 27 | col_27 | placeholder | `xxx`, `xxx`, `xxx` |
| 28 | col_28 | placeholder | `xxx`, `xxx`, `xxx` |

### mallitemmenulistdata

- **Files**: mallitemmenulistdata.txt
- **Rows**: 17
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `#section`, `1`, `1` |
| 1 | col_1 | codename | `ITEMMALL_MENU_LIST`, `1`, `2` |
| 2 | col_2 | codename | ``, `MALL_CONSUME`, `MALL_AVATAR` |
| 3 | col_3 | string | ``, `UIIT_STT_SILKMALL_CONSUMPTION`, `UIIT_STT_SILKMALL_AVATA` |
| 4 | col_4 | path (DDJ) | ``, `interface\mall\mall_item_tab.ddj`, `interface\mall\mall_item_tab.ddj` |
| 5 | col_5 | path (DDJ) | ``, `interface\mall\mall_consum_icon.ddj`, `interface\mall\mall_avatar_icon.ddj` |
| 6 | col_6 | int | ``, `0`, `1` |
| 7 | col_7 | int | ``, `1`, `1` |
| 8 | col_8 | int | ``, `1`, `1` |
| 9 | col_9 | int | ``, `1`, `1` |

### maxtradescaledata

- **Files**: maxtradescaledata.txt
- **Rows**: 6
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `0`, `510`, `918` |

### messagetipdata

- **Files**: messagetipdata.txt
- **Rows**: 175
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | int | `3`, `0`, `0` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `40`, `40`, `40` |
| 5 | col_5 | int | `0`, `0`, `1` |
| 6 | col_6 | string | `SRO_MSGTIP_01`, `SRO_MSGTIP_02`, `SRO_MSGTIP_03` |

### npcchat

- **Files**: npcchat.txt
- **Rows**: 408
- **Columns**: 4

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//Service`, `//%d`, `//xxx` |
| 1 | col_1 | codename | `OwnerCodeName_128`, `%s`, `xxx` |
| 2 | col_2 | codename | `msg1_strid_128`, `%s`, `xxx` |
| 3 | col_3 | codename | `msg2_strid_128`, `%s`, `xxx` |

### optimize_clothes

- **Files**: optimize_clothes.txt
- **Rows**: 12
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//이벤트 코드네임`, `Clothes_event_roc`, `Clothes_event_roc` |
| 1 | col_1 | string | `리전X`, `190`, `190` |
| 2 | col_2 | string | `리전Y`, `102`, `101` |
| 3 | col_3 | string | `아군 의상`, `green`, `green` |
| 4 | col_4 | string | `동맹 의상`, `green`, `green` |
| 5 | col_5 | string | `적군 의상`, `green`, `green` |
| 6 | col_6 | string | `강제성 여부`, `0`, `0` |

### questcontentsdata

- **Files**: questcontentsdata.txt
- **Rows**: 985
- **Columns**: 17

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | codename | `QEVENT_GUIDE`, `QTUTORIAL_CH`, `QSP_ALL_POTION_1` |
| 1 | col_1 | string | `EventGuide(서버전용)`, `중국 튜토리얼`, `재생의 물약 퀘스트` |
| 2 | col_2 | int | `3`, `0`, `0` |
| 3 | col_3 | codename | `xxx`, `xxx`, `xxx` |
| 4 | col_4 | int | `0`, `0`, `1` |
| 5 | col_5 | codename | `xxx`, `SN_CON_QTUTORIAL_CH_01`, `SN_CON_QSP_ALL_POTION_1` |
| 6 | col_6 | codename | `xxx`, `xxx`, `xxx` |
| 7 | col_7 | codename | `xxx`, `xxx`, `xxx` |
| 8 | col_8 | codename | `xxx`, `xxx`, `xxx` |
| 9 | col_9 | codename | `xxx`, `xxx`, `xxx` |
| 10 | col_10 | codename | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | codename | `xxx`, `xxx`, `xxx` |
| 12 | col_12 | codename | `xxx`, `xxx`, `xxx` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `xxx`, `xxx`, `xxx` |
| 15 | col_15 | codename | `xxx`, `xxx`, `xxx` |
| 16 | col_16 | int | `0`, `0`, `0` |

### refabilitybyitemoptleveldata

- **Files**: refabilitybyitemoptleveldata.txt
- **Rows**: 90
- **Columns**: 4

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | int | `24405`, `24405`, `24405` |
| 3 | col_3 | int | `0`, `1`, `2` |

### refaccesspermissionofshop

- **Files**: refaccesspermissionofshop.txt
- **Rows**: 0
- **Columns**: 0

### refconditiontobuyscrapitem

- **Files**: refconditiontobuyscrapitem.txt
- **Rows**: 0
- **Columns**: 0

### refconditiontosellpackageitem

- **Files**: refconditiontosellpackageitem.txt
- **Rows**: 0
- **Columns**: 0

### refconditiontosellscrapitem

- **Files**: refconditiontosellscrapitem.txt
- **Rows**: 0
- **Columns**: 0

### refeventreward

- **Files**: refeventreward.txt
- **Rows**: 0
- **Columns**: 0

### refeventrewarditems

- **Files**: refeventrewarditems.txt
- **Rows**: 0
- **Columns**: 0

### refgachatreeforclientuidata

- **Files**: refgachatreeforclientuidata.txt
- **Rows**: 65
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `3`, `3`, `3` |
| 2 | col_2 | int | `1`, `1`, `1` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `1`, `2`, `3` |
| 5 | col_5 | int | `200`, `200`, `200` |
| 6 | col_6 | string | `UIIT_CTL_WK_CH_ARMOR`, `UIIT_CTL_WK_CH_ARMOR`, `UIIT_CTL_WK_CH_ARMOR` |
| 7 | col_7 | int | `221`, `222`, `223` |
| 8 | col_8 | string | `UIIT_CTL_WK_CH_ARMOR_CLOTHES_1`, `UIIT_CTL_WK_CH_ARMOR_CLOTHES_2`, `UIIT_CTL_WK_CH_ARMOR_CLOTHES_3` |
| 9 | col_9 | int | `11`, `11`, `11` |

### refmagicoptbyitemoptleveldata

- **Files**: refmagicoptbyitemoptleveldata.txt
- **Rows**: 251
- **Columns**: 6

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `2`, `3`, `3` |
| 1 | col_1 | int | `355`, `354`, `355` |
| 2 | col_2 | int | `16`, `17`, `17` |
| 3 | col_3 | int | `0`, `0`, `0` |
| 4 | col_4 | placeholder | `xxx`, `xxx`, `xxx` |
| 5 | col_5 | placeholder | ``, ``, `` |

### refmagicoptgroup

- **Files**: refmagicoptgroup.txt
- **Rows**: 88
- **Columns**: 12

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `1`, `1` |
| 2 | col_2 | int | `1`, `1`, `1` |
| 3 | col_3 | string | `MAGIC_NOR_ROCSET_001`, `MAGIC_NOR_ROCSET_001`, `MAGIC_NOR_ROCSET_001` |
| 4 | col_4 | int | `357`, `358`, `359` |
| 5 | col_5 | int | `10`, `10`, `10` |
| 6 | col_6 | int | `6`, `6`, `60` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | placeholder | `xxx`, `xxx`, `xxx` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | placeholder | ``, ``, `` |

### refmappingshopgroup

- **Files**: refmappingshopgroup.txt
- **Rows**: 92
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | string | `GROUP_MALL`, `GROUP_MALL`, `GROUP_MALL` |
| 3 | col_3 | codename | `MALL_ARCHEMY`, `MALL_AVATAR`, `MALL_CONSUME` |
| 4 | col_4 | placeholder | ``, ``, `` |

### refmappingshopwithtab

- **Files**: refmappingshopwithtab.txt
- **Rows**: 89
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | codename | `MALL_ARCHEMY`, `MALL_AVATAR`, `MALL_CONSUME` |
| 3 | col_3 | codename | `MALL_ARCHEMY_GROUP1`, `MALL_AVATAR_GROUP1`, `MALL_CONSUME_GROUP1` |
| 4 | col_4 | placeholder | ``, ``, `` |

### refoptionalteleport

- **Files**: refoptionalteleport.txt
- **Rows**: 39
- **Columns**: 20

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | string | `콘스탄티노플`, `슬픔의 숲`, `신들의 정원` |
| 3 | col_3 | codename | `SN_ZONE_22004`, `SN_ZONE_25063`, `SN_ZONE_25068` |
| 4 | col_4 | int | `26959`, `27207`, `25416` |
| 5 | col_5 | int | `1030`, `648`, `735` |
| 6 | col_6 | int | `80`, `-21`, `0` |
| 7 | col_7 | int | `512`, `194`, `1674` |
| 8 | col_8 | int | `1`, `1`, `1` |
| 9 | col_9 | int | `-1`, `-1`, `-1` |
| 10 | col_10 | int | `1`, `1`, `1` |
| 11 | col_11 | int | `0`, `0`, `0` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `-1`, `-1`, `-1` |
| 14 | col_14 | placeholder | `xxx`, `xxx`, `xxx` |
| 15 | col_15 | int | `-1`, `-1`, `-1` |
| 16 | col_16 | placeholder | `xxx`, `xxx`, `xxx` |
| 17 | col_17 | int | `-1`, `-1`, `-1` |
| 18 | col_18 | placeholder | `xxx`, `xxx`, `xxx` |
| 19 | col_19 | placeholder | ``, ``, `` |

### refpackageitem

- **Files**: refpackageitem.txt
- **Rows**: 1,727
- **Columns**: 18

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | int | `24639`, `24640`, `24641` |
| 3 | col_3 | string | `PACKAGE_ITEM_CH_SWORD_01_A`, `PACKAGE_ITEM_CH_SWORD_02_A`, `PACKAGE_ITEM_CH_SWORD_03_A` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | string | `EXPAND_TERM_ALL`, `EXPAND_TERM_ALL`, `EXPAND_TERM_ALL` |
| 6 | col_6 | codename | `SN_ITEM_CH_SWORD_01_A`, `SN_ITEM_CH_SWORD_02_A`, `SN_ITEM_CH_SWORD_03_A` |
| 7 | col_7 | codename | `SN_ITEM_CH_SWORD_01_A_TT_DESC`, `SN_ITEM_CH_SWORD_02_A_TT_DESC`, `SN_ITEM_CH_SWORD_03_A_TT_DESC` |
| 8 | col_8 | path (DDJ) | `item\china\weapon\sword_01.ddj`, `item\china\weapon\sword_02.ddj`, `item\china\weapon\sword_03.ddj` |
| 9 | col_9 | int | `-1`, `-1`, `-1` |
| 10 | col_10 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | int | `-1`, `-1`, `-1` |
| 12 | col_12 | placeholder | `xxx`, `xxx`, `xxx` |
| 13 | col_13 | int | `-1`, `-1`, `-1` |
| 14 | col_14 | placeholder | `xxx`, `xxx`, `xxx` |
| 15 | col_15 | int | `-1`, `-1`, `-1` |
| 16 | col_16 | placeholder | `xxx`, `xxx`, `xxx` |
| 17 | col_17 | placeholder | ``, ``, `` |

### refpricepolicyofitem

- **Files**: refpricepolicyofitem.txt
- **Rows**: 2,869
- **Columns**: 15

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | string | `PACKAGE_ITEM_CH_BLADE_01_A`, `PACKAGE_ITEM_CH_BLADE_02_A`, `PACKAGE_ITEM_CH_BLADE_03_A` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | int | `890`, `3500`, `15250` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | placeholder | `xxx`, `xxx`, `xxx` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | placeholder | `xxx`, `xxx`, `xxx` |
| 10 | col_10 | int | `0`, `0`, `0` |
| 11 | col_11 | placeholder | `xxx`, `xxx`, `xxx` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | placeholder | `xxx`, `xxx`, `xxx` |
| 14 | col_14 | placeholder | ``, ``, `` |

### refquestrewarditems

- **Files**: refquestrewarditems.txt
- **Rows**: 340
- **Columns**: 13

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `6`, `10`, `11` |
| 1 | col_1 | codename | `QNO_CH_POTION_1`, `QNO_CH_GENARAL_BO_1`, `QNO_CH_GENARAL_SP_1` |
| 2 | col_2 | int | `0`, `0`, `0` |
| 3 | col_3 | codename | `ITEM_ETC_HP_POTION_01`, `ITEM_ETC_MP_POTION_01`, `ITEM_ETC_ALL_POTION_01` |
| 4 | col_4 | placeholder | `xxx`, `xxx`, `xxx` |
| 5 | col_5 | codename | `xxx`, `xxx`, `xxx` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | int | `28`, `50`, `50` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | placeholder | `xxx`, `xxx`, `xxx` |
| 10 | col_10 | int | `0`, `0`, `0` |
| 11 | col_11 | placeholder | `xxx`, `xxx`, `xxx` |
| 12 | col_12 | placeholder | ``, ``, `` |

### refqusetreward

- **Files**: refqusetreward.txt
- **Rows**: 702
- **Columns**: 26

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `3`, `4`, `5` |
| 1 | col_1 | codename | `QNO_CH_SMITH_1`, `QNO_CH_CHEF_1`, `QNO_CH_SOLDIER_EA1_1` |
| 2 | col_2 | int | `1`, `1`, `1` |
| 3 | col_3 | int | `1`, `1`, `1` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | int | `0`, `0`, `0` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | int | `205`, `475`, `1000` |
| 11 | col_11 | int | `270`, `375`, `2752` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `0`, `0`, `0` |
| 15 | col_15 | placeholder | `xxx`, `xxx`, `xxx` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | int | `0`, `0`, `0` |
| 19 | col_19 | int | `0`, `0`, `0` |
| 20 | col_20 | placeholder | `xxx`, `xxx`, `xxx` |
| 21 | col_21 | int | `0`, `0`, `0` |
| 22 | col_22 | placeholder | `xxx`, `xxx`, `xxx` |
| 23 | col_23 | int | `0`, `0`, `0` |
| 24 | col_24 | placeholder | `xxx`, `xxx`, `xxx` |
| 25 | col_25 | placeholder | ``, ``, `` |

### refrentitem

- **Files**: refrentitem.txt
- **Rows**: 0
- **Columns**: 0

### refrewardpolicytobuyscrapitem

- **Files**: refrewardpolicytobuyscrapitem.txt
- **Rows**: 0
- **Columns**: 0

### refrewardpolicytosellpackageitem

- **Files**: refrewardpolicytosellpackageitem.txt
- **Rows**: 0
- **Columns**: 0

### refrewardpolicytosellscrapitem

- **Files**: refrewardpolicytosellscrapitem.txt
- **Rows**: 0
- **Columns**: 0

### refscrapofpackageitem

- **Files**: refscrapofpackageitem.txt
- **Rows**: 1,727
- **Columns**: 30

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | string | `PACKAGE_ITEM_MALL_BALLOON_A_ROC_DMG_ABS`, `PACKAGE_ITEM_CH_M_HEAVY_01_AA_A`, `PACKAGE_ITEM_CH_W_HEAVY_04_BA_A` |
| 3 | col_3 | codename | `ITEM_MALL_BALLOON_A_ROC_DMG_ABS`, `ITEM_CH_M_HEAVY_01_AA_A`, `ITEM_CH_W_HEAVY_04_BA_A` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | int | `0`, `0`, `0` |
| 6 | col_6 | int | `5`, `48`, `61` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | int | `0`, `0`, `0` |
| 11 | col_11 | int | `0`, `0`, `0` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `0`, `0`, `0` |
| 15 | col_15 | int | `0`, `0`, `0` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | int | `0`, `0`, `0` |
| 19 | col_19 | int | `0`, `0`, `0` |
| 20 | col_20 | int | `-1`, `-1`, `-1` |
| 21 | col_21 | placeholder | `xxx`, `xxx`, `xxx` |
| 22 | col_22 | int | `-1`, `-1`, `-1` |
| 23 | col_23 | placeholder | `xxx`, `xxx`, `xxx` |
| 24 | col_24 | int | `-1`, `-1`, `-1` |
| 25 | col_25 | placeholder | `xxx`, `xxx`, `xxx` |
| 26 | col_26 | int | `-1`, `-1`, `-1` |
| 27 | col_27 | placeholder | `xxx`, `xxx`, `xxx` |
| 28 | col_28 | int | `54648`, `29336`, `30020` |
| 29 | col_29 | placeholder | ``, ``, `` |

### refservereventid

- **Files**: refservereventid.txt
- **Rows**: 4
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `30004`, `30003`, `30002` |

### refsetitemgroup

- **Files**: refsetitemgroup.txt
- **Rows**: 43
- **Columns**: 19

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | codename | `ITEMSET_ROC_CH_M_RED_LIGHTNING`, `ITEMSET_ROC_CH_W_RED_LIGHTNING`, `ITEMSET_ROC_CH_M_RED_THUNDER` |
| 3 | col_3 | string | `붉은번개세트(중국-남)`, `붉은번개세트(중국-여)`, `붉은천둥세트(중국-남)` |
| 4 | col_4 | codename | `SN_ITEMSET_ROC_RED_LIGHTNING`, `SN_ITEMSET_ROC_RED_LIGHTNING`, `SN_ITEMSET_ROC_RED_THUNDER` |
| 5 | col_5 | placeholder | `xxx`, `xxx`, `xxx` |
| 6 | col_6 | int | `0`, `0`, `0` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | int | `0`, `0`, `0` |
| 11 | col_11 | int | `0`, `0`, `0` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `0`, `0`, `0` |
| 15 | col_15 | int | `0`, `0`, `0` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | placeholder | ``, ``, `` |

### refshop

- **Files**: refshop.txt
- **Rows**: 75
- **Columns**: 13

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | int | `965`, `966`, `967` |
| 3 | col_3 | codename | `MALL_CONSUME`, `STORE_CH_SMITH`, `STORE_CH_ARMOR` |
| 4 | col_4 | int | `-1`, `-1`, `-1` |
| 5 | col_5 | placeholder | `xxx`, `xxx`, `xxx` |
| 6 | col_6 | int | `-1`, `-1`, `-1` |
| 7 | col_7 | placeholder | `xxx`, `xxx`, `xxx` |
| 8 | col_8 | int | `-1`, `-1`, `-1` |
| 9 | col_9 | placeholder | `xxx`, `xxx`, `xxx` |
| 10 | col_10 | int | `-1`, `-1`, `-1` |
| 11 | col_11 | placeholder | `xxx`, `xxx`, `xxx` |
| 12 | col_12 | placeholder | ``, ``, `` |

### refshopgoods

- **Files**: refshopgoods.txt
- **Rows**: 2,294
- **Columns**: 14

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | codename | `MALL_ARCHEMY_ASTRAL`, `MALL_ARCHEMY_ASTRAL`, `MALL_ARCHEMY_ASTRAL` |
| 3 | col_3 | string | `PACKAGE_ITEM_ETC_ARCHEMY_MAGICSTONE_A...`, `PACKAGE_ITEM_ETC_ARCHEMY_MAGICSTONE_A...`, `PACKAGE_ITEM_ETC_ARCHEMY_MAGICSTONE_A...` |
| 4 | col_4 | int | `0`, `1`, `2` |
| 5 | col_5 | int | `-1`, `-1`, `-1` |
| 6 | col_6 | placeholder | `xxx`, `xxx`, `xxx` |
| 7 | col_7 | int | `-1`, `-1`, `-1` |
| 8 | col_8 | placeholder | `xxx`, `xxx`, `xxx` |
| 9 | col_9 | int | `-1`, `-1`, `-1` |
| 10 | col_10 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | int | `-1`, `-1`, `-1` |
| 12 | col_12 | placeholder | `xxx`, `xxx`, `xxx` |
| 13 | col_13 | placeholder | ``, ``, `` |

### refshopgroup

- **Files**: refshopgroup.txt
- **Rows**: 92
- **Columns**: 13

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | int | `977`, `978`, `979` |
| 3 | col_3 | string | `GROUP_MALL_CONSUME`, `GROUP_STORE_CH_SMITH`, `GROUP_STORE_CH_ARMOR` |
| 4 | col_4 | codename | `xxx`, `NPC_CH_SMITH`, `NPC_CH_ARMOR` |
| 5 | col_5 | int | `-1`, `-1`, `-1` |
| 6 | col_6 | placeholder | `xxx`, `xxx`, `xxx` |
| 7 | col_7 | int | `-1`, `-1`, `-1` |
| 8 | col_8 | placeholder | `xxx`, `xxx`, `xxx` |
| 9 | col_9 | int | `-1`, `-1`, `-1` |
| 10 | col_10 | placeholder | `xxx`, `xxx`, `xxx` |
| 11 | col_11 | int | `-1`, `-1`, `-1` |
| 12 | col_12 | placeholder | `xxx`, `xxx`, `xxx` |

### refshopitemstockperiod

- **Files**: refshopitemstockperiod.txt
- **Rows**: 137
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | string | `GROUP_MALL`, `GROUP_MALL`, `GROUP_MALL` |
| 3 | col_3 | string | `PACKAGE_ITEM_ETC_E091216_PINE`, `PACKAGE_ITEM_ETC_E100630_VIETNAM_FLAG`, `PACKAGE_ITEM_MALL_AVATAR_M_ADMIRAL` |
| 4 | col_4 | string | `2010-12-26 10:00:00`, `2010-07-01 00:00:00`, `2011-11-20 06:00:00` |
| 5 | col_5 | string | `2011-01-30 10:00:00`, `2010-10-30 00:00:00`, `2011-12-20 06:00:00` |
| 6 | col_6 | int | `0`, `0`, `0` |

### refshoptab

- **Files**: refshoptab.txt
- **Rows**: 208
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | int | `2397`, `2398`, `2399` |
| 3 | col_3 | codename | `MALL_CONSUME_SPECIAL`, `MALL_CONSUME_SCROLL`, `MALL_CONSUME_POTION` |
| 4 | col_4 | codename | `MALL_CONSUME_GROUP1`, `MALL_CONSUME_GROUP1`, `MALL_CONSUME_GROUP1` |
| 5 | col_5 | codename | `UIIT_STT_SILKMALL_SPECIAL`, `UIIT_STT_SILKMALL_SCROLL`, `UIIT_STT_SILKMALL_POTION` |
| 6 | col_6 | placeholder | ``, ``, `` |

### refshoptabgroup

- **Files**: refshoptabgroup.txt
- **Rows**: 88
- **Columns**: 6

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `15`, `15`, `15` |
| 2 | col_2 | int | `1056`, `1057`, `1058` |
| 3 | col_3 | codename | `MALL_CONSUME_GROUP1`, `MALL_AVATAR_GROUP1`, `MALL_PET_GROUP1` |
| 4 | col_4 | codename | `UIIT_STT_SILKMALL_CONSUMPTION`, `UIIT_STT_SILKMALL_AVATA`, `UIIT_STT_SILKMALL_PET` |
| 5 | col_5 | placeholder | ``, ``, `` |

### refsiegeblessbuff

- **Files**: refsiegeblessbuff.txt
- **Rows**: 9
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | int | `1`, `1`, `1` |
| 3 | col_3 | int | `32088`, `32089`, `32093` |
| 4 | col_4 | int | `700000`, `700000`, `120000` |
| 5 | col_5 | int | `1800`, `1800`, `800` |
| 6 | col_6 | placeholder | ``, ``, `` |

### refsiegedungeon

- **Files**: refsiegedungeon.txt
- **Rows**: 4
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `3`, `6` |
| 2 | col_2 | int | `61`, `61`, `61` |
| 3 | col_3 | int | `2`, `2`, `2` |
| 4 | col_4 | int | `600000`, `600000`, `600000` |
| 5 | col_5 | int | `3000`, `3000`, `3000` |
| 6 | col_6 | placeholder | ``, ``, `` |

### refskillbyitemoptleveldata

- **Files**: refskillbyitemoptleveldata.txt
- **Rows**: 154
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `89`, `90`, `1` |
| 1 | col_1 | int | `31141`, `31141`, `31142` |

### reftreatitemofshop

- **Files**: reftreatitemofshop.txt
- **Rows**: 0
- **Columns**: 0

### regioncode

- **Files**: regioncode.txt
- **Rows**: 1
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `⼯敓癲捩॥敒楧湯䤠ॄ潃敤丠浡॥਍ऱ㌲㘹ऴ硸ॸ硸൸ㄊ㈉㈴〲砉硸砉硸਍ऱ㌲...` |

### regioninfo

- **Files**: regioninfo.txt
- **Rows**: 1
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | string | `吣坏ॎ떵﯀뚸므उउഉㄊ㈸㤉श䱁ौउഉऊउउഉऊउउഉ⌊䥆䱅ॄ략니꿁搉湯桷...` |

### shopgroupdata

- **Files**: shopgroupdata.txt
- **Rows**: 65
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | codename | `MALL_CONSUME_GROUP1`, `MALL_AVATAR_GROUP1`, `MALL_PET_GROUP1` |
| 3 | col_3 | codename | `UIIT_STT_SILKMALL_CONSUMPTION`, `UIIT_STT_SILKMALL_AVATA`, `UIIT_STT_SILKMALL_PET` |
| 4 | col_4 | placeholder | ``, ``, `` |

### shopitemdata

- **Files**: shopitemdata.txt
- **Rows**: 1,392
- **Columns**: 16

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `579`, `579`, `579` |
| 2 | col_2 | int | `71`, `74`, `77` |
| 3 | col_3 | int | `0`, `0`, `0` |
| 4 | col_4 | int | `0`, `0`, `0` |
| 5 | col_5 | int | `1`, `1`, `1` |
| 6 | col_6 | int | `1`, `1`, `1` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | int | `0`, `0`, `0` |
| 10 | col_10 | int | `0`, `0`, `0` |
| 11 | col_11 | int | `0`, `0`, `0` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `0`, `0`, `0` |
| 15 | col_15 | int | `0`, `0`, `0` |

### shopitemstockquantity

- **Files**: shopitemstockquantity.txt
- **Rows**: 0
- **Columns**: 0

### shoptabdata

- **Files**: shoptabdata.txt
- **Rows**: 161
- **Columns**: 5

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `579`, `580`, `581` |
| 2 | col_2 | codename | `STORE_CH_SMITH_TAB1`, `STORE_CH_SMITH_TAB2`, `STORE_CH_SMITH_TAB3` |
| 3 | col_3 | int | `8`, `8`, `8` |
| 4 | col_4 | codename | `SN_TAB_WEAPON`, `SN_TAB_SHIELD`, `SN_TAB_ETC` |

### siegefortress

- **Files**: siegefortress.txt
- **Rows**: 4
- **Columns**: 15

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `3`, `6` |
| 2 | col_2 | string | `FORTRESS_JANGAN`, `FORTRESS_HOTAN`, `FORTRESS_BIJEOKDAN` |
| 3 | col_3 | string | `????`, `????`, `?????` |
| 4 | col_4 | codename | `SN_FORTRESS_JANGAN`, `SN_FORTRESS_HOTAN`, `SN_FORTRESS_BIJEOKDAN` |
| 5 | col_5 | codename | `GATE_CH`, `GATE_KT`, `GATE_CH` |
| 6 | col_6 | int | `0`, `0`, `1` |
| 7 | col_7 | int | `300`, `300`, `200` |
| 8 | col_8 | int | `30`, `30`, `15` |
| 9 | col_9 | int | `25`, `25`, `20` |
| 10 | col_10 | int | `63`, `63`, `96` |
| 11 | col_11 | int | `1000000`, `1000000`, `500000` |
| 12 | col_12 | path (DDJ) | `etc\fort_jangan.ddj`, `etc\fort_hotan.ddj`, `etc\fort_bijeokdan.ddj` |
| 13 | col_13 | codename | `NPC_CH_FORTRESS_OFFICIAL`, `NPC_KT_FORTRESS_OFFICIAL`, `NPC_CH_FORTRESS_OFFICIAL` |
| 14 | col_14 | placeholder | ``, ``, `` |

### siegefortressbattlerank

- **Files**: siegefortressbattlerank.txt
- **Rows**: 7
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `2`, `3` |
| 2 | col_2 | string | `???`, `?????`, `????` |
| 3 | col_3 | int | `45`, `75`, `135` |
| 4 | col_4 | int | `21234`, `21235`, `21236` |
| 5 | col_5 | path (DDJ) | `etc\rank_assault_soilder.ddj`, `etc\rank_elite_assault_soilder.ddj`, `etc\rank_centurion.ddj` |
| 6 | col_6 | placeholder | ``, ``, `` |

### siegefortressguard

- **Files**: siegefortressguard.txt
- **Rows**: 3,641
- **Columns**: 4

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `1`, `1` |
| 2 | col_2 | int | `19210`, `19211`, `19212` |
| 3 | col_3 | placeholder | ``, ``, `` |

### siegefortressitemforge

- **Files**: siegefortressitemforge.txt
- **Rows**: 33
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | int | `1`, `1`, `1` |
| 2 | col_2 | int | `10588`, `10591`, `10592` |
| 3 | col_3 | int | `1500000`, `6667`, `33334` |
| 4 | col_4 | int | `6819`, `122`, `477` |
| 5 | col_5 | int | `450`, `7`, `11` |
| 6 | col_6 | placeholder | ``, ``, `` |

### siegefortressreward

- **Files**: siegefortressreward.txt
- **Rows**: 5
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//`, `// Service`, `1` |
| 1 | col_1 | string | `요새 코드네임 GUST참고`, `FortressCodeName`, `FORTRESS_HOTAN` |
| 2 | col_2 | string | `마을 입장 메시지에 요새전 점령 길드 이름 표시 (regioncod...`, `DependentCityRegionCodeName`, `RN_OA_OASISKINGDOM` |
| 3 | col_3 | string | `월드맵에 길드문장 띄우는 좌표`, `RGx`, `135` |
| 4 | col_4 | string | ``, `RGy`, `96` |
| 5 | col_5 | string | ``, `PosX`, `6` |
| 6 | col_6 | string | ``, `PosY`, `28` |

### siegestructupgradedata

- **Files**: siegestructupgradedata.txt
- **Rows**: 63
- **Columns**: 8

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `1`, `1`, `1` |
| 1 | col_1 | string | `STRUCTURE_BIG_GATE_JA_01`, `STRUCTURE_BIG_GATE_JA_02`, `STRUCTURE_BIG_GATE_JA_03` |
| 2 | col_2 | string | `STRUCTURE_BIG_GATE_JA_01`, `STRUCTURE_BIG_GATE_JA_01`, `STRUCTURE_BIG_GATE_JA_01` |
| 3 | col_3 | string | `STRUCTURE_BIG_GATE_JA_02`, `STRUCTURE_BIG_GATE_JA_03`, `STRUCTURE_BIG_GATE_JA_04` |
| 4 | col_4 | string | `xxx`, `xxx`, `xxx` |
| 5 | col_5 | string | `xxx`, `xxx`, `xxx` |
| 6 | col_6 | string | `xxx`, `xxx`, `xxx` |
| 7 | col_7 | placeholder | ``, ``, `` |

### skilldata_10000enc

- **Files**: skilldata_10000enc.txt
- **Rows**: 268
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葊꫇෼哕⁗혉鬠ᚕ犵쁚�룲陬黽싐劺㩎ꏜ偛蹛劫彾⯴싹釞饞睢퐶鲭棔�...`, `殒ｹ싱䫫䟷빥⺆糽얉颎缚ꘂ闟궫뜏꣧ᔉ푰빪䦵傝歔屋歾戮讬Ў⣱瞅癦�ඎ䉧炫䫉...`, `䱃砏槍ঙ겱鿷㸏巛겂佼ﭼ喞᧶�㐘쩟㍇莧ᶋ剱荿䜥㔬懝�ᄐꨭ톐聯ᔮ悽ṚㄤＶ哶...` |

### skilldata_15000enc

- **Files**: skilldata_15000enc.txt
- **Rows**: 285
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葆꫇෼哕⁾훢鬋ᙺ牳쁤�룯陙黶싟劺㩛ꏔ偔蹭劓彽⯯숕釰饢睌푆鳈棲�...`, `೛咝暖轞�硴膯邁敫馓筐থ䊲燗照δᄯ�걲턞ᮡ뉟ࠊꇁ읹潻暝＆輘␆ꁐ...`, `켯仫貮ྎ㔎휵䃹틜蜳켎膜꛷㗻꾸⒣쁸Ῠ뵆ἳ扄샦쟃兗걓ꑃ⧞ᵌ䧧髣防멶찠ₜ౤㿵팢ꃜ...` |

### skilldata_20000enc

- **Files**: skilldata_20000enc.txt
- **Rows**: 225
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葆꫌෼哕⁾훢鯡ᚖ犽쁜�룲陙鸉싅勊㩓ꎾ偝蹥力彺⯽숕釱饩睒퐾鳂棦�...`, `㌮５奸氙컣鯚䪴覻ݩ거猔ᶾ榱ޕ챋譋뼡虿⩕뮳櫶಴�餂㭁⋇蹒終熓滌ڍ娚�...`, `礴掄憪톸络耷쩘쉳儡尐틱䘆㎧嘃⤬₶苦꘤覆ꙛ扖ࣲ훴숻걢ⲝ鸰౸諒㓸贱곅שׂ...` |

### skilldata_25000enc

- **Files**: skilldata_25000enc.txt
- **Rows**: 232
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葇꫇෼哕⁾훢鯡ᚉ犽쁜�룲陙鸉싅勊㩓ꏆ健蹔劤彯⬊싼釦饤睈표鳄棱�...`, `殹ｹ숡䫄䜞븾⻄簠엋颧罝ꘞ锵귀띛ꠖᕗ풉뺻䧆僦歨岡殔林诨П⡇瞥皬�ී䊽炼䨟...`, `랓䃶ჶꊥ섆᫡睅钕齬ﴜቍ㒂⏀幚喜骥댨ˈ꿔䩉脷輋Ĺ塕焍䝌혋㒀ⲁ步䕁ﳬ⯤...` |

### skilldata_30000enc

- **Files**: skilldata_30000enc.txt
- **Rows**: 243
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葇꫌෼哕⁾훢鯡ᚅ犽쁜�룲陙鸉싃勄㩛ꏄ偠蹔劤彯⬊싻釲饱睅푔鳓棒�...`, `孻裫餐䪽坿ᎍﴧ嘍䴅姝瀥扱낶콟⾪︧鞅줖ﳺ쨬᫟ᗒ쨎메栙꨻㡜㿛娈䄪컿搵ࣉ閯...`, `䰘砛榷দ겠鼭㸘崑걵例﮲喔ᤍ�㐢쪇㌞菫᷺効荿䜧㕗懦�ᄐꨭ톑肙ᔲ悽ṜㄤＶ哶...` |

### skilldata_35000enc

- **Files**: skilldata_35000enc.txt
- **Rows**: 136
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葈꫇෼哕⁾훢鬌ᙷ牳쁤�룯陙黶싟勂㩈ꏉ偪蹣劗彿⬊숉釨饛睏표鲺棫�...`, `䚹㉁荢욡國洛ፁ壡햮䎃攸뚕嵡軲뻆赥㹜ꩠ폒矺큥贷杧ﰲᐍ쮬﵌ढ禚찎驚퉏...`, `桧䦬ꪞ跹ᶂ涏뙘쓴倶䡱꣔㹎눡솒㰷Ẳ疰ᾖ⽊輨븁䧟傍㼓�폎꘰ꟙ㋳...` |

### skilldata_5000enc

- **Files**: skilldata_5000enc.txt
- **Rows**: 210
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `냢〢〢葆ꪠ෽哜₀훢鬣ᚋ状쁝�룶院黸싃劽㨬ꎮ倔蹒劑彪⯪슿釰饝睌푉鳓棲�...`, `孻裫餐䪽坿ᎍﴧ嘍䴅姠瀥扲냹쿁⿣ﺊ韁쥩ﰭ쪋ᨕᔷ쨿몧桜ꪩ㢙㼘娽䅚츹撙ࠀ锏...`, `殎휹⩝䢇郩㫑㽝꯸췌룙གꖄ忤햄毷뮬汃甆츒쯬ᶗ痭兛鿻橋덟杴䬓摫孿㹞...` |

### skilldata_virtual

- **Files**: skilldata_virtual.txt
- **Rows**: 0
- **Columns**: 0

### skilleffect

- **Files**: skilleffect.txt
- **Rows**: 8,924
- **Columns**: 29

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `#section`, `//ResourceFileID`, `//Character China` |
| 1 | col_1 | string | `characterInfo`, `ResourceTypeName`, `중국 캐릭터` |
| 2 | col_2 | string | ``, `Size`, `` |
| 3 | col_3 | string | ``, `Ride Type`, `` |
| 4 | col_4 | string | ``, `ride`, `` |
| 5 | col_5 | string | ``, `Die Bsr`, `` |
| 6 | col_6 | string | ``, `Die Effect`, `` |
| 7 | col_7 | string | ``, `DamageBone`, `` |
| 8 | col_8 | string | ``, `DamagePos`, `` |
| 9 | col_9 | string | ``, `BloodType`, `` |
| 10 | col_10 | string | ``, `Dead Effect`, `` |
| 11 | col_11 | string | ``, `환경연출`, `` |
| 12 | col_12 | string | ``, `원거리 타겟 OFFSET`, `` |
| 13 | col_13 | placeholder | ``, ``, `` |
| 14 | col_14 | placeholder | ``, ``, `` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |
| 18 | col_18 | placeholder | ``, ``, `` |
| 19 | col_19 | placeholder | ``, ``, `` |
| 20 | col_20 | placeholder | ``, ``, `` |
| 21 | col_21 | placeholder | ``, ``, `` |
| 22 | col_22 | placeholder | ``, ``, `` |
| 23 | col_23 | placeholder | ``, ``, `` |
| 24 | col_24 | placeholder | ``, ``, `` |
| 25 | col_25 | placeholder | ``, ``, `` |
| 26 | col_26 | placeholder | ``, ``, `` |
| 27 | col_27 | placeholder | ``, ``, `` |
| 28 | col_28 | placeholder | ``, ``, `` |

### skillgroup

- **Files**: skillgroup.txt
- **Rows**: 107
- **Columns**: 7

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//Service`, `1`, `1` |
| 1 | col_1 | string | `계열이름`, `필살검`, `연환검` |
| 2 | col_2 | string | `MasteryID`, `257`, `257` |
| 3 | col_3 | string | `MasteryTempName`, `비천검법101`, `비천검법101` |
| 4 | col_4 | string | `계열 Row`, `0`, `1` |
| 5 | col_5 | string | `Description ID`, `UIIT_STT_MASTERY_GROUP_VI_0`, `UIIT_STT_MASTERY_GROUP_VI_1` |
| 6 | col_6 | path (DDJ) | `ICON`, `skillgroup\china\pack_sword_smash.ddj`, `skillgroup\china\pack_sword_chain.ddj` |

### skillmasterydata

- **Files**: skillmasterydata.txt
- **Rows**: 22
- **Columns**: 13

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//Mastery ID`, `0:무기술일반`, `1:기공술일반` |
| 1 | col_1 | string | `Mastery Name - Do Not Use`, ``, `` |
| 2 | col_2 | string | `MasteryNameCode`, ``, `` |
| 3 | col_3 | string | `GroupNum`, ``, `` |
| 4 | col_4 | string | `Mastery Description ID`, ``, `` |
| 5 | col_5 | string | `Tab Name Code`, ``, `` |
| 6 | col_6 | string | `Type (TabID)`, ``, `` |
| 7 | col_7 | string | `"SkillToolTipType`, ``, `` |
| 8 | col_8 | int | ``, ``, `` |
| 9 | col_9 | int | ``, ``, `` |
| 10 | col_10 | int | ``, ``, `` |
| 11 | col_11 | path (DDJ) | ``, ``, `` |
| 12 | col_12 | path (DDJ) | ``, ``, `` |

### specialnpcdata

- **Files**: specialnpcdata.txt
- **Rows**: 13
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `2010`, `2059`, `2077` |
| 1 | col_1 | codename | `NPC_CH_SPECIAL`, `NPC_WC_SPECIAL`, `NPC_KT_SPECIAL` |

### teleportbuilding

- **Files**: teleportbuilding.txt
- **Rows**: 59
- **Columns**: 58

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `2094`, `2095`, `2096` |
| 2 | col_2 | string | `STORE_CH_GATE`, `STORE_WC_GATE`, `STORE_KT_GATE` |
| 3 | col_3 | string | `????`, `????`, `????` |
| 4 | col_4 | placeholder | `xxx`, `xxx`, `xxx` |
| 5 | col_5 | codename | `SN_NPC_CH_GATE`, `SN_NPC_WC_GATE`, `SN_NPC_KT_GATE` |
| 6 | col_6 | placeholder | `xxx`, `xxx`, `xxx` |
| 7 | col_7 | int | `0`, `0`, `0` |
| 8 | col_8 | int | `0`, `0`, `0` |
| 9 | col_9 | int | `4`, `4`, `4` |
| 10 | col_10 | int | `1`, `1`, `1` |
| 11 | col_11 | int | `1`, `1`, `1` |
| 12 | col_12 | int | `0`, `0`, `0` |
| 13 | col_13 | int | `0`, `0`, `0` |
| 14 | col_14 | int | `3`, `3`, `3` |
| 15 | col_15 | int | `0`, `0`, `0` |
| 16 | col_16 | int | `0`, `0`, `0` |
| 17 | col_17 | int | `0`, `0`, `0` |
| 18 | col_18 | int | `0`, `0`, `0` |
| 19 | col_19 | int | `0`, `0`, `0` |
| 20 | col_20 | int | `0`, `0`, `0` |
| 21 | col_21 | int | `0`, `0`, `0` |
| 22 | col_22 | int | `0`, `0`, `0` |
| 23 | col_23 | int | `0`, `0`, `0` |
| 24 | col_24 | int | `0`, `0`, `0` |
| 25 | col_25 | int | `0`, `0`, `0` |
| 26 | col_26 | int | `0`, `0`, `0` |
| 27 | col_27 | int | `0`, `0`, `0` |
| 28 | col_28 | int | `0`, `0`, `0` |
| 29 | col_29 | int | `0`, `0`, `0` |
| 30 | col_30 | int | `0`, `0`, `0` |
| 31 | col_31 | int | `0`, `0`, `0` |
| 32 | col_32 | int | `-1`, `-1`, `-1` |
| 33 | col_33 | int | `0`, `0`, `0` |
| 34 | col_34 | int | `-1`, `-1`, `-1` |
| 35 | col_35 | int | `0`, `0`, `0` |
| 36 | col_36 | int | `-1`, `-1`, `-1` |
| 37 | col_37 | int | `0`, `0`, `0` |
| 38 | col_38 | int | `-1`, `-1`, `-1` |
| 39 | col_39 | int | `0`, `0`, `0` |
| 40 | col_40 | int | `-1`, `-1`, `-1` |
| 41 | col_41 | int | `25000`, `26521`, `23687` |
| 42 | col_42 | int | `0`, `0`, `0` |
| 43 | col_43 | int | `1254`, `962`, `1131` |
| 44 | col_44 | int | `-6`, `-35`, `305` |
| 45 | col_45 | int | `1374`, `8`, `488` |
| 46 | col_46 | int | `0`, `0`, `0` |
| 47 | col_47 | int | `0`, `0`, `0` |
| 48 | col_48 | int | `100`, `100`, `100` |
| 49 | col_49 | int | `25`, `50`, `50` |
| 50 | col_50 | int | `10`, `40`, `30` |
| 51 | col_51 | int | `0`, `0`, `0` |
| 52 | col_52 | path (BSR) | `xxx`, `xxx`, `xxx` |
| 53 | col_53 | placeholder | `xxx`, `xxx`, `xxx` |
| 54 | col_54 | placeholder | `xxx`, `xxx`, `xxx` |
| 55 | col_55 | string | `FORTRESS_JANGAN`, `FORTRESS_DONWHANG`, `FORTRESS_HOTAN` |
| 56 | col_56 | string | `xxx`, `xxx`, `xxx` |
| 57 | col_57 | int | `0`, `0`, `0` |

### testsml

- **Files**: testsml.txt
- **Rows**: 12
- **Columns**: 1

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `<sml>`, `안녕하세요<br>`, `실크로드온라인의 <fontcolorall(255,255,0,0)>S...` |

### textdata_equip&skill

- **Files**: textdata_equip&skill.txt
- **Rows**: 7,781
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_ITEM_CH_SWORD_01_A_DEF`, `SN_ITEM_CH_BLADE_01_A_DEF`, `SN_ITEM_CH_SPEAR_01_A_DEF` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | string | `Copper Sword`, `Copper Blade`, `Crescent` |

### textdata_object

- **Files**: textdata_object.txt
- **Rows**: 9,568
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_MOB_THIEF_NPC`, `SN_MOB_CH_MANGNYANG`, `SN_MOB_CH_BIGEYEGHOST_CLON` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | string | `Thief`, `Mangyang`, `Small-eyed Ghost` |

### textevent

- **Files**: textevent.txt
- **Rows**: 231
- **Columns**: 18

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_QEV_CH_EVENT_KISAENG_070919`, `SN_QEV_CH_EVENT_KISAENG_071225`, `SN_QEV_CH_EVENT_KISAENG_071030` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | path | `Capture the Flag`, `If it Snows on Christmas~`, `Halloween Day` |
| 10 | col_10 | placeholder | ``, ``, `` |
| 11 | col_11 | placeholder | ``, ``, `` |
| 12 | col_12 | placeholder | ``, ``, `` |
| 13 | col_13 | placeholder | ``, ``, `` |
| 14 | col_14 | placeholder | ``, ``, `` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |

### texthelp

- **Files**: texthelp.txt
- **Rows**: 468
- **Columns**: 19

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | string | `SRO_GGW_PG_GROWTH`, `SRO_GGW_PG_STATP`, `SRO_GGW_PG_MASTERY` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | path | `<sml2><strong>1. Character Developmen...`, `<sml2><strong>2. Stat Points</strong>...`, `<sml2><strong>3. Mastery</strong><br>...` |
| 10 | col_10 | placeholder | ``, ``, `` |
| 11 | col_11 | placeholder | ``, ``, `` |
| 12 | col_12 | placeholder | ``, ``, `` |
| 13 | col_13 | placeholder | ``, ``, `` |
| 14 | col_14 | placeholder | ``, ``, `` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |
| 18 | col_18 | placeholder | ``, ``, `` |

### textquest_otherstring

- **Files**: textquest_otherstring.txt
- **Rows**: 2,807
- **Columns**: 20

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_PAYCON_QTUTORIAL_CH`, `SN_PAYCON_QNO_CH_SMITH_1`, `SN_PAYCON_QNO_CH_CHEF_1` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | path | `<sml2><font color="255,44,15,1">The C...`, `<sml2><strong><font color="255,226,74...`, `<sml2><strong><font color="255,226,74...` |
| 10 | col_10 | placeholder | ``, ``, `` |
| 11 | col_11 | placeholder | ``, ``, `` |
| 12 | col_12 | placeholder | ``, ``, `` |
| 13 | col_13 | placeholder | ``, ``, `` |
| 14 | col_14 | placeholder | ``, ``, `` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |
| 18 | col_18 | placeholder | ``, ``, `` |
| 19 | col_19 | placeholder | ``, ``, `` |

### textquest_queststring

- **Files**: textquest_queststring.txt
- **Rows**: 8,272
- **Columns**: 21

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_TALK_COMMON_OK`, `SN_TALK_COMMON_ACCEPT`, `SN_TALK_COMMON_DENY` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | path (,  ) | `OK`, `Accept`, `Refuse` |
| 10 | col_10 | placeholder | ``, ``, `` |
| 11 | col_11 | placeholder | ``, ``, `` |
| 12 | col_12 | placeholder | ``, ``, `` |
| 13 | col_13 | placeholder | ``, ``, `` |
| 14 | col_14 | placeholder | ``, ``, `` |
| 15 | col_15 | placeholder | ``, ``, `` |
| 16 | col_16 | placeholder | ``, ``, `` |
| 17 | col_17 | placeholder | ``, ``, `` |
| 18 | col_18 | placeholder | ``, ``, `` |
| 19 | col_19 | placeholder | ``, ``, `` |
| 20 | col_20 | placeholder | ``, ``, `` |

### textquest_speech&name

- **Files**: textquest_speech&name.txt
- **Rows**: 4,518
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SN_NPC_CH_SMITH_BS`, `SN_NPC_CH_ARMOR_BS`, `SN_NPC_CH_POTION_BS` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | string | `Don't be hesitant to come here to get...`, `Brace yourself up for a long way. You...`, `With consistent patients swarming in,...` |

### texttooltipdata

- **Files**: texttooltipdata.txt
- **Rows**: 15
- **Columns**: 11

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | codename | `SKILL_MALL_PRE_APRU_4W_01`, `SKILL_MALL_PRE_APRU_GLOBAL_4W_01`, `SKILL_FORT_ASSAULTING_SOILDER` |
| 2 | col_2 | int | `0`, `0`, `0` |
| 3 | col_3 | string | `xxx`, `UIIT_STT_PREMIUM_PREFERRED_GAME_ACCESS`, `xxx` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | placeholder | ``, ``, `` |
| 10 | col_10 | placeholder | ``, ``, `` |

### textuisystem

- **Files**: textuisystem.txt
- **Rows**: 5,372
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | string | `UIC_STT_FONTNAME`, `UIIS_STT_MSG_INSTALL_START`, `UIIS_STT_MSG_INSTALL_FOLDER` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | path (, ]) | `Arial`, `Install 'Silkroad Online'.`, `Install 'Silkroad Online' to the foll...` |

### textzonename

- **Files**: textzonename.txt
- **Rows**: 3,477
- **Columns**: 10

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `24999`, `25000`, `25001` |
| 2 | col_2 | placeholder | ``, ``, `` |
| 3 | col_3 | placeholder | ``, ``, `` |
| 4 | col_4 | placeholder | ``, ``, `` |
| 5 | col_5 | placeholder | ``, ``, `` |
| 6 | col_6 | placeholder | ``, ``, `` |
| 7 | col_7 | placeholder | ``, ``, `` |
| 8 | col_8 | placeholder | ``, ``, `` |
| 9 | col_9 | string | `Jangan`, `Jangan`, `Jangan` |

### usableresobjiddata

- **Files**: usableresobjiddata.txt
- **Rows**: 104
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | int | `1`, `1`, `1` |
| 1 | col_1 | int | `1907`, `1908`, `1909` |

### worldmap_instanceinfo

- **Files**: worldmap_instanceinfo.txt
- **Rows**: 12
- **Columns**: 11

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//CodeName`, `Worldmap_THIEFTOWN`, `Worldmap_DONWHANG` |
| 1 | col_1 | string | `Name(Skip)`, `도적마을`, `돈황석굴던전` |
| 2 | col_2 | string | `RegionLeft`, `182`, `1` |
| 3 | col_3 | string | `RegionTop`, `96`, `128` |
| 4 | col_4 | string | `RegionRight`, `182`, `1` |
| 5 | col_5 | string | `RegionBottom`, `96`, `128` |
| 6 | col_6 | string | `MapRegionX`, `169`, `147` |
| 7 | col_7 | string | `MapRegionZ`, `97`, `106` |
| 8 | col_8 | string | `MapPosX`, `165`, `1620` |
| 9 | col_9 | string | `MapPosY`, `-37`, `474` |
| 10 | col_10 | string | `MapPosZ`, `876`, `48` |

### worldmap_localinfo

- **Files**: worldmap_localinfo.txt
- **Rows**: 1,249
- **Columns**: 22

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `//service`, `//`, `` |
| 1 | col_1 | path | ``, ``, `//` |
| 2 | col_2 | string | `스트링 : `, `1`, `` |
| 3 | col_3 | path | `로컬 시스템`, `로컬 스킬 및 스텟`, `로컬 큰 지역` |
| 4 | col_4 | string | `11`, `12`, `13` |
| 5 | col_5 | string | ``, ``, `` |
| 6 | col_6 | string | ``, ``, `` |
| 7 | col_7 | int | ``, ``, `` |
| 8 | col_8 | string | ``, `Parent Place`, `장안 1` |
| 9 | col_9 | int | ``, ``, `` |
| 10 | col_10 | int | ``, ``, `` |
| 11 | col_11 | int | ``, ``, `` |
| 12 | col_12 | int | ``, ``, `` |
| 13 | col_13 | string | `Pic`, `Size`, `` |
| 14 | col_14 | string | `size`, ``, `` |
| 15 | col_15 | string | `Color`, `_R`, `` |
| 16 | col_16 | string | `Color`, `_G`, `` |
| 17 | col_17 | string | `Color`, `_B`, `` |
| 18 | col_18 | string | `Font`, `Shadow`, `` |
| 19 | col_19 | string | `Font`, `Bold`, `` |
| 20 | col_20 | string | `Font`, `Blur`, `` |
| 21 | col_21 | placeholder | ``, ``, `` |

### worldmap_mapinfo

- **Files**: worldmap_mapinfo.txt
- **Rows**: 59
- **Columns**: 23

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `#section`, `//Map File Info`, `//Map ID` |
| 1 | col_1 | string | `WLocalmap`, ``, `Type 0:Wmap, 1:Local` |
| 2 | col_2 | path | ``, ``, `//Name(Skip)` |
| 3 | col_3 | path (DDJ) | ``, ``, `Addr` |
| 4 | col_4 | path | ``, ``, `Texture Size_x` |
| 5 | col_5 | string | ``, ``, `Texture Size_y` |
| 6 | col_6 | string | ``, ``, `Pic Area_x` |
| 7 | col_7 | string | ``, ``, `Pic Area_y` |
| 8 | col_8 | string | ``, ``, `Draw x` |
| 9 | col_9 | string | ``, ``, `Draw y` |
| 10 | col_10 | string | ``, ``, `리젼 left` |
| 11 | col_11 | string | ``, ``, `top` |
| 12 | col_12 | string | ``, ``, `right` |
| 13 | col_13 | string | ``, ``, `bottom` |
| 14 | col_14 | path | ``, ``, `좌표 LT _ x` |
| 15 | col_15 | path | ``, ``, `좌표 LT _y` |
| 16 | col_16 | string | ``, ``, `좌표 RB_x` |
| 17 | col_17 | codename | ``, ``, `좌표 RB_y` |
| 18 | col_18 | string | ``, ``, `요새월드ID` |
| 19 | col_19 | codename | ``, ``, `로컬 이름 스트링 코드` |
| 20 | col_20 | string | ``, ``, `전체맵버튼타입(1:보임,0:안보임)` |
| 21 | col_21 | string | ``, ``, `한 리젼 크기` |
| 22 | col_22 | string | ``, ``, `` |

### worldmapguidedata

- **Files**: worldmapguidedata.txt
- **Rows**: 764
- **Columns**: 13

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | path | `#section`, `//서비스`, `1` |
| 1 | col_1 | string | ` MAP_MANAGER`, `항목`, `field` |
| 2 | col_2 | codename | ``, `시작 리전`, `46x113` |
| 3 | col_3 | path (DDJ) | `0`, `끝 리전`, `17x26` |
| 4 | col_4 | string | ``, `그림 한장의 사이즈`, `128x128` |
| 5 | col_5 | string | ``, `한 리전크기`, `4x4` |
| 6 | col_6 | string | ``, ``, `` |
| 7 | col_7 | string | ``, ``, `` |
| 8 | col_8 | string | ``, ``, `` |
| 9 | col_9 | string | ``, ``, `` |
| 10 | col_10 | string | ``, ``, `` |
| 11 | col_11 | string | ``, ``, `` |
| 12 | col_12 | string | ``, ``, `` |

### worldmapguidedata_region

- **Files**: worldmapguidedata_region.txt
- **Rows**: 268
- **Columns**: 2

| # | Name | Type | Samples |
|---|------|------|---------|
| 0 | col_0 | codename | `MOB_DH_BUGGHOST_CLON`, `MOB_DH_WORKEARTHGHOST_CLON`, `MOB_DH_BUGGHOST` |
| 1 | col_1 | string | `128x127,128x126`, `127x128,127x127,129x128,129x127`, `128x127,128x126` |
