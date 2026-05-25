# **Himmelmez | 希默梅斯**

**[ Saint No. 4 | 神使之肆 ]**

凡人之生死,不过是女神赐予我的棋子。

---

## **Update History**
- **[26-05-14] r1581014** - https://www.taptap.cn/moment/803947045760011278
  - Initial release
---

## **Feature Skill**

### ![skill_4880001][skill_4880001] **Master of Puppetry | 傀儡之主** #4880
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 7 |
| **Damage Type** | Physical |
| | |
#### **Description**
Himmelmez can command The Terrifying Thing from the abyss to attack enemies. After using 【Command Ready】, 【The Terrifying Thing】lurks around Himmelmez to perform an ambush, every second dealing physical damage equal to P.ATK * <b style="color: blue">[2800% / 3200% / 3600% / 4000% / 4400% / 4800% / 5200%]</b> to all enemies within the ring area, and forcefully reducing their movement speed by <b style="color: blue">[50% / 55% / 60% / 65% / 70% / 75% / 80%]</b>. 【The Terrifying Thing】 is 8 meters, the width of the ring is 4 meters, and the patrol radius of The Terrifying Thing can be changed through 【Abyssal Emerge】.

**Lv4** During 【Command, Shadow Follow】, the collision radius of The Terrifying Thing increases by 2 meters.

**Lv7** When attacking only one enemy, the damage of 【The Terrifying Thing】 increases by 50%.

Obtain skill 【Soul Revive】: When 【The Terrifying Thing】 kills, executes, or continuously attacks a player 5 times within 10 sec, it can seize the opponent's soul, lasting for 30 sec; Himmelmez can convert the soul into a puppet, the puppet will copy all attributes of the target player, is treated as Himmelmez's summon, and will fight on its own, lasting for 25 sec.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4880007,
	NameZh = "傀儡之主",
	Level = 7,
	Icon = "skill_4880001",
	Cost = 1,
	Desc = { { id = 4880000, params = { 5200, 80 } } },
	DamageType = 1,
	Logic = "SkillNone",
	Buff = { self = { 142160, 142161, 142162, 142210, 142192 } },
	Pvp_buff = { self = { 142160, 142161, 142162, 142210, 142192 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142160</summary>
<pre><code>{
	id = 142160,
	BuffName = "获得【号令·战斗】",
	BuffRate = { Odds = 100 },
	BuffEffect = { LevelUp = 1, SkillID = 4893001, retain = 1, type = "GetSkill" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142161</summary>
<pre><code>{
	id = 142161,
	BuffName = "获得【号令·扩张】",
	BuffRate = { Odds = 100 },
	BuffEffect = { LevelUp = 1, SkillID = 4894001, retain = 1, type = "GetSkill" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142162</summary>
<pre><code>{
	id = 142162,
	BuffName = "获得【号令·警戒】",
	BuffRate = { Odds = 100 },
	BuffEffect = { LevelUp = 1, SkillID = 4895001, retain = 1, type = "GetSkill" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142210</summary>
<pre><code>{
	id = 142210,
	BuffName = "获得【灵魂苏生】",
	BuffRate = { Odds = 100 },
	BuffEffect = { LevelUp = 1, SkillID = 4905001, retain = 1, type = "GetSkill" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142192</summary>
<pre><code>{ id = 142192, BuffName = "7级特性", BuffRate = { Odds = 100 } }
</code></pre>
</details>

---

## **Skills**

### ![skill_4881001][skill_4881001] **Piercing Judgment | 穿刺之刑** #4881
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| **Damage Type** | Physical Undead |
| **Target** | Enemy SkillTargetRect |
| **Range** | 7.5 m |
| **Skill CD** | 3.0 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | <b style="color: blue">1200 HP / 1600 HP / 2000 HP / 2400 HP / 2800 HP / 3200 HP / 3600 HP / 4000 HP / 4400 HP / 4800 HP</b> |
| | |
#### **Description**
Himmelmez brandishes the demonic sword, summoning hellish bone spikes to pierce through the ground, dealing physical damage equal to P.ATK * <b style="color: blue">[1540% / 1780% / 2020% / 2260% / 2500% / 2740% / 2980% / 3220% / 3460% / 3700%]</b> to the target and enemnies along the path; if the is within the patrol range of 【The Terrifying Thing】, releases 【Piercing Judgment】 toward the target once again, dealing physical damage of the same multiplier.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4881010,
	NameZh = "穿刺之刑",
	Level = 10,
	Icon = "skill_4881001",
	Cost = 1,
	Desc = { { id = 4881000, params = { 3700 } } },
	RollType = 1,
	DamageType = 1,
	SkillType = "Attack",
	Camps = "Enemy",
	Launch_Range = 7.5,
	Fire_EP = 2,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 3,
	SkillCost = { hp = 4800 },
	DelayCD = 1.5,
	Logic = "SkillTargetRect",
	Logic_Param = {
		distance = 8,
		emit = {
			effect_logic = { effect = "sfx_himemmeth_kszw_floor_prf", interval = 0.01, random_axis_y = true, type = 1 },
			speed = 30,
			type = 1,
		},
		forward_offset = 0,
		no_select = 1,
		range_num = 10,
		width = 3,
	},
	Damage = { { damChangePer = 37, elementparam = 9, type = 83501 } },
	DamTime = { type = 1, value = 1 },
	Buff = { enemy = { 142030 } },
	Pvp_buff = { enemy = { 142030 } },
	CastAct = "reading",
	AttackAct = { "use_skill" },
	SE_attack = "Skill/sfx_skill_Himelmez_impale",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142030</summary>
<pre><code>{
	id = 142030,
	BuffName = "穿刺之刑-可怖协同",
	BuffRate = { Odds = 100 },
	BuffEffect = { Odds = 100, coord_attack_range = 8, id = 4897001, type = "HorribleThingCoordUseSkill" },
}
</code></pre>
</details>

---

### ![skill_4882001][skill_4882001] **Rebel Mandate | 逆权篡令** #4882
#### **Details**
| | |
|-|-:|
| **Type** | HellPlant |
| **Max Lv** | 5 |
| **Damage Type** | Physical |
| **Target** | Enemy SkillSelfRange |
| **Fixed CT** | 1.5 sec |
| **Fixed CD** | 30.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 5000 HP |
| | |
#### **Description**
After a fixed casting time of 1.5 sec, unfold a domain of usurped authority, the domain radius is 8m, enemies close to the edge of the domain will continuously receive attacks from bone spikes, dealing physical damage equal to P.ATK * <b style="color: blue">[540% / 720% / 900% / 1080% / 1260%]</b>; enemies attempting to leave the domain will be forcefully stunned for 2.5 sec, the stun effect can take effect at most once every 15 sec. 【Rebel Mandate】 will apply 【Revel】 to all living summons within the range, causing them to attack their nearest ally, dealing physical damage equal to Himmelmez's P.ATK * 1000%. 【The Terrifying Thing】 is immune to 【Rebel】, and summons that are already under 【Rebel】 cannot be affected again; the cooldown time is fixed and cannot be reduced.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4882005,
	NameZh = "逆权篡令",
	Level = 5,
	Icon = "skill_4882001",
	Cost = 1,
	Desc = { { id = 4882000, params = { 1260 } } },
	DamageType = 1,
	SkillType = "HellPlant",
	Camps = "Enemy",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 30,
	FixCD = 1,
	SkillCost = { hp = 5000 },
	DelayCD = 1,
	Lead_Type = { CCT = 1.5, FCT = 0, type = 2 },
	Logic = "SkillSelfRange",
	Logic_Param = {
		duration = 15,
		fieldarea_cannot_immune = 1,
		hit = 50,
		interval = 0.3,
		interval_skills = { 4907005, 4908005 },
		isNpcTrap = 1,
		isTimeTrap = 1,
		lastTime = 15,
		max_count = 1,
		no_select = 1,
		npcid = 1729,
		range = 8,
	},
	CastAct = "reading",
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Himelmez_usurp",
}
</code></pre>
</details>

---

### ![skill_4883001][skill_4883001] **Divine Retribution | 神使之怒** #4883
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| **Damage Type** | Physical Undead |
| **Target** | Enemy SkillSelfRange |
| **Range** | 4.0 m |
| **Fixed CT** | 0.8 sec |
| **Variable CT** | 4.0 sec |
| **Skill CD** | 12.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | <b style="color: blue">1500 HP / 2000 HP / 2500 HP / 3000 HP / 3500 HP / 4000 HP / 4500 HP / 5000 HP / 5500 HP / 6000 HP</b> |
| | |
#### **Description**
Himmelmez unleahes fury toward enemies attempting to approach her, dealing physical damage equal to P.ATK * <b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b> to enemies within a 5-meter radius around her and knocking them back 4 meters, ignoring Endure effects, and leaving behind bone spikes in the knockback area that last for 5 sec, dealing physical damage equal to P.ATK * <b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b> every second.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4883010,
	NameZh = "神使之怒",
	Level = 10,
	Icon = "skill_4883001",
	Cost = 1,
	Desc = { { id = 4883000, params = { 3500, 3500 } } },
	RollType = 1,
	DamageType = 1,
	SkillType = "Attack",
	Camps = "Enemy",
	Launch_Range = 4,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 12,
	SkillCost = { hp = 6000 },
	DelayCD = 2,
	Lead_Type = { CCT = 0.8, FCT = 4, type = 2 },
	Logic = "SkillSelfRange",
	Logic_Param = {
		count = 10,
		fieldarea_cannot_immune = 1,
		interval = 0.5,
		isCountTrap = 1,
		max_count = 1,
		no_select = 1,
		range = 4,
		trap_effect = "sfx_himemmeth_nszn_prf,LowRange_B",
		whitelist = 1,
	},
	Damage = { { damChangePer = 35, elementparam = 9, type = 83501 } },
	DamTime = { type = 1, value = 1 },
	HitEffects = { { direction = "back", distance = 4, ignore_no_hit_back = 1, only_first_hitback = 1, speed = 20, type = 1 } },
	CastAct = "reading",
	AttackAct = { "use_skill4" },
	SE_attack = "Skill/sfx_skill_Himelmez_wrath",
}
</code></pre>
</details>

---

### ![skill_4884001][skill_4884001] **Netherworld Passage | 黄泉引渡** #4884
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| **Damage Type** | Physical Undead |
| **Target** | Enemy SkillPointRange |
| **Range** | 9.0 m |
| **Variable CT** | 3.0 sec |
| **Skill CD** | 15.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | 3000 HP |
| | |
#### **Description**
Opens a gate of death in a designated area, zombie hands reach out from underground, dealing physical damage equal to P.ATK * <b style="color: blue">[800% / 900% / 1000% / 1100% / 1200% / 1300% / 1400% / 1500% / 1600% / 1700%]</b> every second to enemies within the range, lasting for 5 sec, and applies 【Immobilize】 for 1; if the target resists 【Immobilize】, forcefully reduces their movement speed by 80%.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4884010,
	NameZh = "黄泉引渡",
	Level = 10,
	Icon = "skill_4884001",
	Cost = 1,
	Desc = { { id = 4884000, params = { 1700 } } },
	RollType = 1,
	DamageType = 1,
	SkillType = "Attack",
	Camps = "Enemy",
	Launch_Range = 9,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 15,
	SkillCost = { hp = 3000 },
	DelayCD = 2,
	Lead_Type = { CCT = 0, FCT = 3, type = 2 },
	Logic = "SkillPointRange",
	Logic_Param = {
		count = 5,
		duration = 5,
		interval = 1,
		isCountTrap = 1,
		max_count = 1,
		no_select = 1,
		range = 3,
		range_num = 10,
		trap_effect = "sfx_himemmeth_hqzw_prf,LowRange_B",
	},
	Damage = { { damChangePer = 17, elementparam = 9, type = 83501 } },
	DamTime = { type = 1, value = 1 },
	Buff = { enemy = { 142130 } },
	Pvp_buff = { enemy = { 142130 } },
	CastAct = "reading",
	AttackAct = { "use_skill5" },
	SE_attack = "Skill/sfx_skill_Himelmez_ferry",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142130</summary>
<pre><code>{
	id = 142130,
	BuffName = "黄泉之握（定身）",
	BuffRate = { Odds = { a = 0, b = 100, type = 160 } },
	BuffType = { isdisperse = 1, isgain = 0 },
	BuffStateID = 90020,
	BuffEffect = { NoMove = 1, StateEffect = 9, type = "StatusChange" },
}
</code></pre>
</details>

---

### ![skill_4885001][skill_4885001] **Evil God's Domain | 邪神乐园** #4885
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 5 |
| **Target** | Friend/Enemy SkillSelfRange |
| **Range** | 7.0 m |
| **Variable CT** | 3.0 sec |
| **Fixed CD** | 28.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | 8000 HP |
| | |
#### **Description**
Creates a domain of death, all players and summons within a 5-meter radius of the target area will not die, lasting for <b style="color: blue">[6 / 7 / 8 / 9 / 10]</b> sec; the shield effects (shield values) of all enemies within the range will temporarily become ineffective during the duration, the cooldown time is fixed and cnnot be reduced.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4885005,
	NameZh = "邪神乐园",
	Level = 5,
	Icon = "skill_4885001",
	Cost = 1,
	Desc = { { id = 4885000, params = { 10 } } },
	SkillType = "Buff",
	Camps = "Friend|Enemy",
	Launch_Range = 7,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 28,
	FixCD = 1,
	SkillCost = { hp = 8000 },
	DelayCD = 2,
	Lead_Type = { CCT = 0, FCT = 3, type = 2 },
	Logic = "SkillSelfRange",
	Logic_Param = {
		count = 10,
		fieldarea_cannot_immune = 1,
		interval = 1,
		isCountTrap = 1,
		max_count = 1,
		no_select = 1,
		range = 5,
		trap_effect = "sfx_himemmeth_wsdly_prf,LowRange_B",
		whitelist = 1,
	},
	Buff = { enemy = { 142060, 142061, 142062 }, friend = { 142061 }, self_skill = { 142061 }, team = { 142061 } },
	Pvp_buff = { enemy = { 142060, 142061, 142062 }, friend = { 142061 }, self_skill = { 142061 }, team = { 142061 } },
	CastAct = "reading",
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Himelmez_pandemonium",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142060</summary>
<pre><code>{ id = 142060, BuffName = "伪神乐园-护盾禁用UI", BuffRate = { Odds = 100 }, BuffEffect = {
	type = "DisableShield",
} }
</code></pre>
</details>
<details>
<summary>BUFFER #142061</summary>
<pre><code>{
	id = 142061,
	BuffName = "伪神乐园-免死",
	BuffRate = { Odds = { a = 0, b = 100, type = 3070 } },
	BuffEffect = { sync_nine = 1, type = "Undead" },
	BuffIcon = "skillbuff_4885001",
	IconType = 1,
	BuffDesc = "邪神乐园：免死且护盾值失效",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142062</summary>
<pre><code>{
	id = 142062,
	BuffName = "伪神乐园-生命上限降低",
	BuffRate = { Odds = { a = 0, b = 100, type = 3070 } },
	BuffStateID = 141460,
	BuffEffect = { MaxHpPer = { a = 0, b = 0, c = 223141, type = 5020 }, type = "AttrChange" },
}
</code></pre>
</details>

---

### ![skill_4886001][skill_4886001] **Blood Decree | 噬血裁决** #4886
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| **Target** | Friend SkillNone |
| **Variable CT** | 3.0 sec |
| **Skill CD** | 15.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | 10000 HP |
| | |
#### **Description**
Himmelmez enhances her demonic blade with the blood of the dead, increasing her Phy Pen and Ign Def by <b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b>, her attacks have a <b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b> chance to apply a forced 【Bleeding】 state, lasts for 5 sec; 【Blood Decree】 lasts for 600 sec, and when using job skills during the duration, additionally consumes 5% of current HP.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4886010,
	NameZh = "噬血裁决",
	Level = 10,
	Icon = "skill_4886001",
	Cost = 1,
	Desc = { { id = 4886000, params = { 30, 30 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 15,
	SkillCost = { hp = 10000 },
	DelayCD = 2,
	AutoCondition = { { no_target = 1, time = 600, type = 1 } },
	Lead_Type = { CCT = 0, FCT = 3, type = 2 },
	Logic = "SkillNone",
	Buff = { self = { 142070, 142071, 142074, 142075 } },
	Pvp_buff = { self = { 142070, 142071, 142074, 142075 } },
	CastAct = "reading",
	AttackAct = { "use_skill6" },
	SE_attack = "Skill/sfx_skill_Himelmez_condemn",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142070</summary>
<pre><code>{
	id = 142070,
	BuffName = "鲜血之刃-生命替代消耗",
	BuffRate = { Odds = 100 },
	Condition = { need_skill = { 4881, 4882, 4883, 4884, 4885, 4886, 4887, 4893, 4894, 4895, 4905 }, type = "UseSkill" },
	BuffEffect = { id = { 142076 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142071</summary>
<pre><code>{
	id = 142071,
	BuffName = "鲜血之刃(流血）",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, type = "Attack" },
	BuffEffect = { id = { 142072, 142073 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142074</summary>
<pre><code>{
	id = 142074,
	BuffName = "鲜血之刃增伤",
	BuffRate = { Odds = 100 },
	BuffEffect = { DamSpike = { a = 0.03, b = 0, type = 1 }, IgnoreDef = { a = 0.03, b = 0, type = 1 }, type = "AttrChange" },
	BuffIcon = "skillbuff_4889001",
	IconType = 1,
	BuffDesc = "噬血裁决：技能额外消耗生命",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142075</summary>
<pre><code>{
	id = 142075,
	BuffName = "鲜血之刃",
	BuffRate = { Odds = 100 },
	BuffEffect = { RightHand = 400300, priority = 1, type = "PartTransform" },
}
</code></pre>
</details>

---

### ![skill_4887001][skill_4887001] **Descent of the End | 终焉降临** #4887
#### **Details**
| | |
|-|-:|
| **Type** | HorribleAddBuff |
| **Max Lv** | 1 |
| **Target** | Friend SkillNone |
| **Variable CT** | 3.0 sec |
| **Fixed CD** | 75.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | 12000 HP |
| | |
#### **Description**
Himmelmez awakens the power of death within her body to enter her ultimate form, during 【Descent of the End】 she loses 10% of her current HP every second, and the effect of 【Immortal Body】 doubles; 【Descent of the End】 will awaken 【The Terrifying Thing】, causing it to display its true form, and every 0.5 sec dealing damage of the same multiplier as 【Master of Puppetry】 to enemies it collides with, lasts 30 sec, the cooldown time is fixed and cannot be reduced; during the duration 【The Terrifying Thing】 obtains several enhanced effects:

【The Terrifying Thing】's collision damage will execute enemies with HP below 25% (does not work against monsters)

※ When 【The Terrifying Thing】 kills an enemy, all of its damage increases by 20% for 10 sec, this effect stacks

※ Can use Command, Shadow Follow to make 【The Terrifying Thing】 to stop moving for 5 sec.

Himmelmez is immune to the execution effect of enemy's 【The Terrifying Thing】; 【Descent of the End】 can only be used when 【The Terrifying Thing】 is summoned.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4887001,
	NameZh = "终焉降临",
	Level = 1,
	Icon = "skill_4887001",
	Cost = 1,
	Contidion = { skillid = 4883003 },
	Desc = { { id = 4887000, params = _EmptyTable } },
	SkillType = "HorribleAddBuff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 2,
	Attack_EP = 2,
	CD = 75,
	FixCD = 1,
	SkillCost = { hp = 12000 },
	DelayCD = 2,
	PreCondition = { { buffid = 142002, type = 12 } },
	Lead_Type = { CCT = 0, FCT = 3, type = 2 },
	Logic = "SkillNone",
	Logic_Param = { buffIDs = { 142145, 142146, 142252 } },
	Buff = { self = { 142140, 142141, 142153 } },
	Pvp_buff = { self = { 142140, 142141, 142153 } },
	CastAct = "reading",
	AttackAct = { "use_skill7" },
	SE_attack = "Skill/sfx_skill_Himelmez_advent",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142140</summary>
<pre><code>{
	id = 142140,
	BuffName = "死亡圆舞曲",
	BuffRate = { Odds = 100 },
	BuffStateID = 142140,
	BuffIcon = "skillbuff_4887001",
	IconType = 1,
	BuffDesc = "终焉降临",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142141</summary>
<pre><code>{ id = 142141, BuffName = "死亡圆舞曲", BuffRate = { Odds = 100 }, BuffEffect = {
	id = { 142142 },
	type = "AddBuff",
} }
</code></pre>
</details>
<details>
<summary>BUFFER #142153</summary>
<pre><code>{
	id = 142153,
	BuffName = "击杀",
	BuffRate = { Odds = 100 },
	Condition = { entryKind = 0, type = "IamKiller" },
	BuffEffect = { id = { 142143 }, type = "AddBuff" },
}
</code></pre>
</details>

---

### ![skill_4888001][skill_4888001] **Dark Coronation | 邪神加冕** #4888
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
Himmelmez's skills and 【The Terrifying Thing】, including all living summons in the party, damage is increased by <b style="color: blue">[10% / 20% / 30% / 40% / 50%]</b>; whenever any living summon dies within a 12-meter radius, this effect will increase for herself by <b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b>, lasts 30 sec and can stack.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4888005,
	NameZh = "邪神加冕",
	Level = 5,
	Icon = "skill_4888001",
	Cost = 1,
	Desc = { { id = 4888000, params = { 50, 10 } } },
	Buff = { self = { 142100 } },
	Pvp_buff = { self = { 142100 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142100</summary>
<pre><code>{
	id = 142100,
	BuffName = "希默-亡灵女王-附近召唤物阵亡",
	BuffRate = { Odds = 100 },
	Condition = {
		npcids = {
			580050,
			580070,
			580071,
			580072,
			580073,
			580074,
			580101,
			580102,
			580103,
			580104,
			580105,
			580203,
			580204,
			590010,
			590020,
			590030,
			591010,
			591020,
			591030,
			600010,
			600011,
			600020,
			600021,
			600030,
			600031,
			580310,
			580400,
			580700,
			580701,
		},
		range = 12,
		type = "NearSummonDie",
	},
	BuffEffect = { id = { 142101 }, type = "AddBuff" },
	ShareTeamBuff = 142102,
}
</code></pre>
</details>

---

### ![skill_4889001][skill_4889001] **Weeping Blood Echo | 泣血回响** #4889
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
Whenever Himmelmez kills an enemy, restores <b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b> of her Max HP, and when killing a player, the restored amount increases to <b style="color: blue">[2% / 4% / 6% / 8% / 10% / 12% / 14% / 16% / 18% / 20%]</b>; When Himmelmez suffers HP Loss or consumes HP to use skills, enemies within a 6-meter radius will suffer 50% of the equivalent HP Loss and the HP lost by herself will be converted into a stackable shield at 100% value, lasts 15 sec, this shield cannot block HP Loss damage.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4889010,
	NameZh = "泣血回响",
	Level = 10,
	Icon = "skill_4889001",
	Cost = 1,
	Desc = { { id = 4889000, params = { 5, 20 } } },
	Buff = { self = { 142080, 142090, 142110, 142112, 142114 } },
	Pvp_buff = { self = { 142080, 142090, 142110, 142112, 142114 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142080</summary>
<pre><code>{
	id = 142080,
	BuffName = "希默-泣血-流失转护盾",
	BuffRate = { Odds = 100 },
	BuffEffect = { Ratio = 1, shield_buffid = 142081, type = "HpLossToShield" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142090</summary>
<pre><code>{
	id = 142090,
	BuffName = "希默-泣血-近距分摊伤害",
	BuffRate = { Odds = 100 },
	BuffEffect = { Ratio = 0.5, range = 6, type = "HpLossToNearbyDamage" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142110</summary>
<pre><code>{
	id = 142110,
	BuffName = "泣血",
	BuffRate = { Odds = 100 },
	Condition = { entryKind = 2, type = "IamKiller" },
	BuffEffect = { id = { 142111 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142112</summary>
<pre><code>{
	id = 142112,
	BuffName = "泣血",
	BuffRate = { Odds = 100 },
	Condition = { entryKind = 1, type = "IamKiller" },
	BuffEffect = { id = { 142113 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142114</summary>
<pre><code>{ id = 142114, BuffName = "攻击回血", BuffRate = { Odds = 100 } }
</code></pre>
</details>

---

### ![skill_4890001][skill_4890001] **Immortal Body | 不灭之躯** #4890
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
Himmelmez for every 10% HP lost will obtain <b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b> Final DMG Reduc, Skill DMG Reduc and Auto Attack DMG Reduc; for every 1000 HP lost, increases her own P.ATK by <b style="color: blue">[1 / 2 / 3 / 4 / 5]</b> points (this effect is only 25% in PVP/GVG). The healing received by Himmelmez cannot be transferred or converted into damage.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4890005,
	NameZh = "不灭之躯",
	Level = 5,
	Icon = "skill_4890001",
	Cost = 1,
	Desc = { { id = 4890000, params = { 10, 5 } } },
	Buff = { self = { 142120, 142122 } },
	Pvp_buff = { self = { 142120, 142122 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142120</summary>
<pre><code>{ id = 142120, BuffName = "不灭之躯", BuffRate = { Odds = 100 }, BuffEffect = {
	id = { 142121 },
	type = "AddBuff",
} }
</code></pre>
</details>
<details>
<summary>BUFFER #142122</summary>
<pre><code>{
	id = 142122,
	BuffName = "治愈之光不会转移转换",
	BuffRate = { Odds = 100 },
	BuffEffect = { skillid = { 0 }, type = "HealNoAffect" },
}
</code></pre>
</details>

---

### ![skill_4891001][skill_4891001] **Fall of Blasphemy | 亵神之殇** #4891
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
When Himmelmez and 【The Terrifying Thing】 deals damage, they reduce the the enemy's P.Def by <b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b>, stakcs up to 10 times. When the target takes physical damage, overflowing Ignore P.Def will be converted to additional damage, increasing up to 50% (attacks that already ignore P.Def such as critical hits are not applicable).

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4891010,
	NameZh = "亵神之殇",
	Level = 10,
	Icon = "skill_4891001",
	Cost = 1,
	Desc = { { id = 4891000, params = { 5 } } },
	Buff = { self = { 142190 } },
	Pvp_buff = { self = { 142190 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142190</summary>
<pre><code>{
	id = 142190,
	BuffName = "深入骨髓",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, buff_skill_can_trigger = 1, type = "Attack" },
	BuffEffect = { id = { 142191 }, type = "AddBuff" },
}
</code></pre>
</details>

---

### ![skill_4892001][skill_4892001] **Fallen Angel | 堕落天使** #4892
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 1 |
| | |
#### **Description**
Himmelmez's race changes to Angel, and her attack element is forcefully set to Undead element; when calculating elemental coefficients, the coefficient of Undead attribute against Lv1 Element armor changes to (2 - original coeffecient), and other effects that increase element coefficient attributes will be calculated additionally after this.

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4892001,
	NameZh = "堕落天使",
	Level = 1,
	Icon = "skill_4892001",
	Cost = 1,
	Contidion = { skillid = 4886003 },
	Desc = { { id = 4892000, params = _EmptyTable } },
	Buff = { self = { 142180 } },
	Pvp_buff = { self = { 142180 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142180</summary>
<pre><code>local a =
	{ id = 142180, BuffName = "死亡天使", BuffRate = { Odds = 100 }, BuffEffect = { race = 8, type = "ChangeRace" } }
</code></pre>
</details>

---

## **Advanced Runes**

### S-Star Runes

#### Piercing Mark - Star Rune | 穿刺之印·星符文 #379484
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Piercing Judgment】 Damage +<b style="color:blue">[1.0% ~ 60.0%]</b>
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

#### Mark of the End - Star Rune | 终焉之印·星符文 #379485
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- When The Terrifying Thing hits enemies repeatedly, Damage +<b style="color:blue">[1% ~ 20%]</b>, stacks up to 3 times
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

#### Nether Mark - Star Rune | 黄泉之印·星符文 #379486
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- Enemies applied with 【Blood Decree】's  【Bleeding】 causes healing effects received by enemies <b style="color:blue">[-1.0% ~ -30.0%]</b>
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

---

### S Runes

#### Divine Envoy Mark Rune | 神使之印符文 #379487
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Divine Retribution】 Cooldown <b style="color:blue">[-1% ~ -20%]</b>
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

#### Mark of the Evil God Rune | 邪神之印符文 #379488
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Evil God's Domain】, Max HP of enemies within the range <b style="color:blue">[-1.0% ~ -20.0%]</b>
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

#### Rebel Mandate's Mark Rune 逆权之印符文 #379489
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Rebel Mandate】 bone spike Damage +<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【Master of Puppetry】 Feature Lv +1 (Generation Probability: 6%)

---

## **Featured Weapon**

---

## **Equipment**

---

## **Aesir Runes**
| Prop Name | Var Name | Value |
| :- | :- | -: |
| Str | Str | 25 |
| Dex | Dex | 10 |
| VIT | Vit | 30 |
| Atk | Atk | 1618.8 |
| Dmg% | AtkPer | 20.0% |
| Def | Def | 187.5 |
| Def% | DefPer | 17.0% |
| M.Def | MDef | 84.6 |
| M.Def% | MDefPer | 13.0% |
| MaxHp | MaxHp | 16221 |
| MaxHp% | MaxHpPer | 12.0% |
| Hit | Hit | 90 |
| Crit.Res. | CriRes | 45.3 |
| Refine Atk | Refine | 225.7 |
| Move Spd% | MoveSpdPer | 10.0% |
| Dmg Reduc. | DamReduc | 12.0% |
| Magic Reduc. | MDamReduc | 8.0% |
| Ignore Def | IgnoreDef | 16.0% |
| Phy. Dmg Inc.  | DamIncrease | 15.0% |
| Pen. | DamSpike | 10.0% |
| Undead Element Damage | UndeadAtk | 15.0% |
| Demi-Human Re. | DemiHumanResPer | 10.0% |


[rune_0]: ../img/rune_0.png
[rune_1]: ../img/rune_1.png
[rune_2]: ../img/rune_2.png
[rune_3]: ../img/rune_3.png
[skill_4880001]: ../img/skill_4880001.png
[skill_4881001]: ../img/skill_4881001.png
[skill_4882001]: ../img/skill_4882001.png
[skill_4883001]: ../img/skill_4883001.png
[skill_4884001]: ../img/skill_4884001.png
[skill_4885001]: ../img/skill_4885001.png
[skill_4886001]: ../img/skill_4886001.png
[skill_4887001]: ../img/skill_4887001.png
[skill_4888001]: ../img/skill_4888001.png
[skill_4889001]: ../img/skill_4889001.png
[skill_4890001]: ../img/skill_4890001.png
[skill_4891001]: ../img/skill_4891001.png
[skill_4892001]: ../img/skill_4892001.png
