# **黑白熊 | 黑白熊**

**[ undefined | undefined ]**

undefined

---

## **Update History**
- **[26-05-14] r1581014** - https://www.taptap.cn/moment/803947045760011278
  - Initial release
---

## **Feature Skill**

### ![skill_4920001][skill_4920001] **Desperate Executor | 绝望的执行者** #4920
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 7 |
| | |
#### **Description**
当黑白熊亲自击倒一名玩家时，会由一个【黑白熊分身】对目标进行【特别体罚】，【特别体罚】持续<b style="color: blue">[4 / 5 / 6 / 7 / 8 / 9 / 10]</b>秒，【特别体罚】会使目标来回承受不同的【体罚】效果，且期间目标无法复活，战斗列表内有多个黑白熊时，效果不会叠加；黑白熊会基于当前敌人和自身当前地图队内存活人数差值获得伤害增幅和伤害减免，每相差一人增加<b style="color: blue">[3.0% / 3.5% / 4.0% / 4.5% / 5.0% / 5.5% / 6.0%]</b>，魔物始终视为孤军作战，减伤比率不会超过90%；江之岛盾子会始终计入存活人数中

**Lv4** 自身召唤各类【黑白熊分身】也会算作存活的队友

**Lv7** 在【特别体罚】的最后增加【宇宙旅行】；【宇宙旅行】期间，目标将在5秒内从战场中驱逐，对MVP/Mini无效

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4920007,
	NameZh = "绝望的执行者",
	Level = 7,
	Icon = "skill_4920001",
	Cost = 1,
	Desc = { { id = 4920000, params = { 6, 10 } } },
	Buff = { self = { 142450, 142454, 142550 } },
	Pvp_buff = { self = { 142450, 142454, 142550 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142450</summary>
<pre><code>{
	id = 142450,
	BuffName = "绝望的执行者（击杀玩家）",
	BuffRate = { Odds = 100 },
	Condition = { entryKind = 1, type = "IamKiller" },
	BuffEffect = { Odds = 100, id = { 142455 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142454</summary>
<pre><code>{
	id = 142454,
	BuffName = "特性（空buff)",
	BuffRate = { Odds = 100 },
	BuffEffect = { sync_nine = 1, type = "AttrChange" },
	ShareTeamBuff = 142462,
}
</code></pre>
</details>
<details>
<summary>BUFFER #142550</summary>
<pre><code>{
	id = 142550,
	BuffName = "特性提升处刑",
	BuffRate = { Odds = 100 },
	BuffEffect = { duration = { a = 0.5, b = 0, type = 1 }, skillID = { 4936 }, type = "AffactSkill" },
}
</code></pre>
</details>

---

## **Skills**

### ![skill_4921001][skill_4921001] **Black and White Bear Bomb | 黑白熊炸弹** #4921
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| **Damage Type** | Physical Fire |
| **Target** | Enemy SkillPointRange |
| **Range** | 9.0 m |
| **Skill CD** | 2.5 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | <b style="color: blue">120 SP / 135 SP / 150 SP / 165 SP / 180 SP / 195 SP / 210 SP / 225 SP / 240 SP / 255 SP</b> |
| | |
#### **Description**
投掷一个【自爆黑白熊】，在目标点造成（物理攻击+自身灵巧*自身智力/5）*<b style="color: blue">[700% / 800% / 900% / 1000% / 1100% / 1200% / 1300% / 1400% / 1500% / 1600%]</b>的火属性物理伤害，并降低目标30%火属性伤害减免，持续10秒，【自爆黑白熊】会在自爆5次后消失

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4921010,
	NameZh = "黑白熊炸弹",
	Level = 10,
	Icon = "skill_4921001",
	Cost = 1,
	Desc = { { id = 4921000, params = { 1600 } } },
	RollType = 1,
	DamageType = 1,
	SkillType = "Attack",
	Camps = "Enemy",
	Launch_Range = 9,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 2.5,
	SkillCost = { sp = 255 },
	DelayCD = 1.5,
	Logic = "SkillPointRange",
	Logic_Param = {
		duration = 5,
		fieldarea_cannot_immune = 1,
		hit = 5,
		interval = 1,
		isTimeTrap = 1,
		max_count = 5,
		no_select = 1,
		range = 5,
		trap_effect = "sfx_danganmonokuma_hbxzd_buff_prf",
	},
	Damage = { { damChangePer = 16, elementparam = 4, type = 84501 } },
	DamTime = { type = 1, value = 1 },
	Buff = { enemy = { 142400 } },
	Pvp_buff = { enemy = { 142400 } },
	AttackAct = { "use_skill" },
	SE_attack = "Skill/sfx_skill_Monokuma_Bomb",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142400</summary>
<pre><code>{
	id = 142400,
	BuffName = "黑白熊炸弹-火属性易伤",
	BuffRate = { Odds = 100 },
	BuffType = { isdisperse = 1, isgain = 0 },
	BuffEffect = { BeFireDamPer = -0.3, type = "AttrChange" },
	BuffIcon = "skillbuff_commonbuff",
	IconType = 1,
	BuffDesc = "受到火属性伤害提高",
	Dsc = "受到火属性伤害提高",
}
</code></pre>
</details>

---

### ![skill_4922001][skill_4922001] **Restricted Area | 禁止通行的区域** #4922
#### **Details**
| | |
|-|-:|
| **Type** | BlazarTrap |
| **Max Lv** | 5 |
| **Target** | Enemy SkillPointRange |
| **Range** | 8.0 m |
| **Skill CD** | 20.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 120 SP |
| | |
#### **Description**
黑白熊在目标区域中心召唤一个【嘲讽黑白熊】，持续<b style="color: blue">[30 / 30 / 30 / 30 / 30]</b>秒，禁止区域内的所有敌人释放技能，且每秒有<b style="color: blue">[11% / 12% / 13% / 14% / 15%]</b>概率对敌人添加【嘲讽】使其攻击嘲讽黑白熊，【嘲讽黑白熊】在受到超过<b style="color: blue">[30 / 30 / 30 / 30 / 30]</b>次攻击后会提前消失

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4922005,
	NameZh = "禁止通行的区域",
	Level = 5,
	Icon = "skill_4922001",
	Cost = 1,
	Desc = { { id = 4922000, params = { 15, 30, 30 } } },
	SkillType = "BlazarTrap",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 20,
	SkillCost = { sp = 120 },
	DelayCD = 1,
	Logic = "SkillPointRange",
	Logic_Param = {
		duration = 11,
		fieldarea_cannot_immune = 1,
		interval = 1,
		isNpcTrap = 1,
		isTimeTrap = 1,
		lastTime = 11,
		max_count = 1,
		no_select = 1,
		npcid = 580410,
		range = 5,
		skillid = 4939001,
		suspend_can_immune = 1,
	},
	AttackAct = { "use_skill2" },
	SE_attack = "Skill/sfx_skill_Monokuma_Area_Forbidden",
}
</code></pre>
</details>

---

### ![skill_4923001][skill_4923001] **Elusive and unpredictable | 神出鬼没** #4923
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| **Target** | Friend SkillNone |
| **Skill CD** | 30.0 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | 99 SP |
| | |
#### **Description**
黑白熊神秘的幕后操作者使其在战场中来去自如，难以捉摸；黑白熊隐藏身形，且无法被锁定，所有技能射程增加<b style="color: blue">[5% / 10% / 15% / 20% / 25% / 30% / 35% / 40% / 45% / 50%]</b>，冷却时间降低<b style="color: blue">[5% / 10% / 15% / 20% / 25% / 30% / 35% / 40% / 45% / 50%]</b>（与其他降低技能冷却效果叠加时，降低效果不超过50%），可以在移动时召唤【黑白熊分身】来代替自身释放技能，持续<b style="color: blue">[120 / 120 / 120 / 120 / 120 / 120 / 120 / 120 / 120 / 120]</b>秒；【神出鬼没】与【校长的权威】无法共存

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4923010,
	NameZh = "神出鬼没",
	Level = 10,
	Icon = "skill_4923001",
	Cost = 1,
	Desc = { { id = 4923000, params = { 50, 50, 120 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 30,
	SkillCost = { sp = 99 },
	DelayCD = 1.5,
	NoTargetAutoCast = 1,
	Logic = "SkillNone",
	Logic_Param = { no_target = 1 },
	Buff = { self = { 142420, 142421, 142422, 142423, 142424, 142425 } },
	Pvp_buff = { self = { 142420, 142421, 142422, 142423, 142424, 142425 } },
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Monokuma_Elusive",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142420</summary>
<pre><code>{
	id = 142420,
	BuffName = "神出鬼没-幕后状态",
	BuffRate = { Odds = 100 },
	BuffType = { isdisperse = 0, isgain = 1 },
	BuffStateID = 142420,
	BuffEffect = {
		AtkDistancePer = { a = 0.05, b = 0, type = 1 },
		CDChangePerWithBound = { a = -0.05, b = 0, type = 1 },
		MoveSpdPer = { a = 0, b = 0, c = 223201, type = 5020 },
		type = "AttrChange",
	},
	BuffIcon = "skillbuff_commonbuff",
	IconType = 1,
	BuffDesc = "幕后状态：射程提高，冷却降低，隐藏身形",
	Dsc = "幕后状态：射程提高，冷却降低，隐藏身形",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142421</summary>
<pre><code>{
	id = 142421,
	BuffName = "神出鬼没-不可锁定",
	BuffRate = { Odds = 100 },
	BuffType = { isdisperse = 0, isgain = 1 },
	BuffEffect = { sync_nine = 1, type = "NoEnemyLocked" },
	BuffIcon = "skillbuff_commonbuff",
	IconType = 1,
	BuffDesc = "幕后状态：无法被敌方锁定",
	Dsc = "幕后状态：无法被敌方锁定",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142422</summary>
<pre><code>{
	id = 142422,
	BuffName = "神出鬼没-删除校长权威",
	BuffRate = { Odds = 100 },
	BuffEffect = { id = { 142430, 142431, 142432, 142433, 142434, 142435, 142436 }, type = "DelBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142423</summary>
<pre><code>{
	id = 142423,
	BuffName = "神出鬼没-喊话",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, no_normal_skill = 1, type = "UseSkillEnd" },
	BuffEffect = {
		live_time = 3,
		monokuma_effect = "Skill/sfx_danganmonokuma_jwdzxz_floor_prf",
		special_skill_ids = { 4921, 4922, 4923, 4925, 4926, 4927, 4928 },
		type = "MonokumaSkillAnnounce",
	},
}
</code></pre>
</details>
<details>
<summary>BUFFER #142424</summary>
<pre><code>{
	id = 142424,
	BuffName = "神出鬼没-移动施法",
	BuffRate = { Odds = 100 },
	BuffEffect = { skillids = { 4921, 4922, 4923, 4925, 4926, 4927, 4928 }, type = "CanMoveUseSkill" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142425</summary>
<pre><code>{
	id = 142425,
	BuffName = "神出鬼没-移动施法",
	BuffRate = { Odds = 100 },
	BuffEffect = { all_skill = 1, type = "NoActionUseSkill" },
}
</code></pre>
</details>

---

### ![skill_4924001][skill_4924001] **The Authority of the Principal | 校长的权威** #4924
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| **Target** | Friend SkillNone |
| **Skill CD** | 30.0 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | 99 SP |
| | |
#### **Description**
黑白熊散发其呆萌外表下可怕的内在气场，黑白熊体型增大100%，获得<b style="color: blue">[45% / 50% / 55% / 60% / 65% / 70% / 75% / 80% / 85% / 90%]</b>的技能伤害增幅和伤害减免效果，持续<b style="color: blue">[5 / 10 / 15 / 20 / 25 / 30 / 35 / 40 / 45 / 50]</b>秒；每次受到攻击时，效果会减少1%，每次造成伤害时，效果会增加1%，不会超过技能的初始效果，也不会低于<b style="color: blue">[120% / 120% / 120% / 120% / 120% / 120% / 120% / 120% / 120% / 120%]</b>，【神出鬼没】与【校长的权威】无法共存

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4924010,
	NameZh = "校长的权威",
	Level = 10,
	Icon = "skill_4924001",
	Cost = 1,
	Desc = { { id = 4924000, params = { 90, 120, 50 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 30,
	SkillCost = { sp = 99 },
	DelayCD = 1.5,
	NoTargetAutoCast = 1,
	Logic = "SkillNone",
	Logic_Param = { no_target = 1 },
	Buff = { self = { 142431, 142432, 142433, 142434, 142435, 142436 } },
	Pvp_buff = { self = { 142431, 142432, 142433, 142434, 142435, 142436 } },
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Monokuma_Authority_Master",
	FashionAttackAct = "use_skill",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142431</summary>
<pre><code>{
	id = 142431,
	BuffName = "校长的权威-保底效果",
	BuffRate = { Odds = 100 },
	BuffType = { isdisperse = 0, isgain = 1 },
	BuffStateID = 142431,
	BuffEffect = { SkillDam = { a = 0, b = 0, c = 223211, type = 5020 }, end_del_buff = { 142430 }, sync_nine = 1, type = "AttrChange" },
	Dsc = "校长权威：保底伤害和减免",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142432</summary>
<pre><code>{
	id = 142432,
	BuffName = "校长的权威-体型增大",
	BuffRate = { Odds = 100 },
	BuffType = { isdisperse = 0, isgain = 1 },
	BuffEffect = { addper = 1, type = "ChangeScale" },
	Dsc = "校长权威：体型增大",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142433</summary>
<pre><code>{
	id = 142433,
	BuffName = "校长的权威-初始加层",
	BuffRate = { Odds = 100 },
	BuffEffect = { layer = { { id = 142430, layer = { a = 5, b = 50, type = 1 } } }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142434</summary>
<pre><code>{
	id = 142434,
	BuffName = "校长的权威-造成伤害加层",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, buff_skill_can_trigger = 1, need_damage = 1, type = "Attack" },
	BuffEffect = { layer = { { id = 142430, layer = 1 } }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142435</summary>
<pre><code>{
	id = 142435,
	BuffName = "校长的权威-受击减层",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, buff_skill_can_trigger = 1, type = "BeAttack" },
	BuffEffect = { Odds = 100, id = { 142437 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142436</summary>
<pre><code>{
	id = 142436,
	BuffName = "校长的权威-删除神出鬼没",
	BuffRate = { Odds = 100 },
	BuffEffect = { id = { 142420, 142421, 142422, 142423, 142424, 142425 }, type = "DelBuff" },
}
</code></pre>
</details>

---

### ![skill_4925001][skill_4925001] **Scapegoat | 替罪羔羊** #4925
#### **Details**
| | |
|-|-:|
| **Type** | ScapegoatSkill |
| **Max Lv** | 5 |
| **Target** | Team/Enemy SkillNone |
| **Range** | 5.0 m |
| **Skill CD** | 25.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 72 SP |
| | |
#### **Description**
选择一名敌人或者友方，将自身受到的实际伤害的<b style="color: blue">[50% / 50% / 50% / 50% / 50%]</b>转移给目标，持续<b style="color: blue">[4 / 5 / 6 / 7 / 8]</b>秒，如果没有选择目标，会在原地召唤一个【装死黑白熊】来转移伤害；【装死黑白熊】在持续时间内受到致命伤害也不会死亡

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4925005,
	NameZh = "替罪羔羊",
	Level = 5,
	Icon = "skill_4925001",
	Cost = 1,
	Desc = { { id = 4925000, params = { 50, 8 } } },
	SkillType = "ScapegoatSkill",
	Camps = "Team|Enemy",
	Launch_Range = 5,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 25,
	SkillCost = { sp = 72 },
	DelayCD = 1,
	Logic = "SkillNone",
	Logic_Param = { no_target_skill_id = 4937005, select_target = 1, select_type = 1 },
	Buff = { enemy = { 142440 }, self = { 142443, 142444 }, team = { 142440 } },
	Pvp_buff = { enemy = { 142440 }, self = { 142443, 142444 }, team = { 142440 } },
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Monokuma_Scapegoat",
	FashionAttackAct = "use_skill",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142440</summary>
<pre><code>{
	id = 142440,
	BuffName = "替罪羔羊-伤害转移",
	BuffRate = { Odds = 100 },
	BuffStateID = 142440,
	BuffEffect = { transfer_ratio = 1, type = "Scapegoat" },
	BuffIcon = "skillbuff_commonbuff",
	IconType = 1,
	BuffDesc = "替罪羔羊：转移伤害",
	Dsc = "替罪羔羊：转移伤害",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142443</summary>
<pre><code>{ id = 142443, BuffName = "替罪羔羊-伤害转移自身", BuffRate = { Odds = 100 }, BuffStateID = 142443 }
</code></pre>
</details>
<details>
<summary>BUFFER #142444</summary>
<pre><code>{
	id = 142444,
	BuffName = "替罪羔羊-减伤",
	BuffRate = { Odds = 100 },
	Condition = { nobuffid = { 142442 }, type = "HasBuff" },
	BuffType = { isdisperse = 0, isgain = 1 },
	BuffEffect = { BaWangRate = 0.5, sync_nine = 1, type = "AttrChange" },
}
</code></pre>
</details>

---

### ![skill_4926001][skill_4926001] **Preparation for Corporal Punishment | 体罚准备** #4926
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 1 |
| **Damage Type** | HP Loss |
| **Target** | Enemy SkillLockedTarget |
| **Range** | 8.0 m |
| **Skill CD** | 24.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 200 SP |
| | |
#### **Description**
黑白熊选择一个敌人作为体罚的目标物，在<b style="color: blue">[20]</b>秒内每秒对其造成物理攻击*<b style="color: blue">[15%]</b>的火属性生命流失，并使其受到的火属性伤害增加<b style="color: blue">[600%]</b>；如果目标在持续时间内阵亡，则必定触发【特别体罚】；如果敌人身上的【绝望】已经达到上限，则会立即斩杀目标并释放【特别体罚】

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4926001,
	NameZh = "体罚准备",
	Level = 1,
	Icon = "skill_4926001",
	Cost = 1,
	Desc = { { id = 4926000, params = { 15, 600, 20 } } },
	DamageType = 4,
	SkillType = "Buff",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 24,
	SkillCost = { sp = 200 },
	DelayCD = 1,
	Logic = "SkillLockedTarget",
	Buff = { enemy = { 142530, 142531, 142532, 142533 } },
	Pvp_buff = { enemy = { 142530, 142531, 142532, 142533 } },
	AttackAct = { "use_skill3" },
	SE_attack = "Skill/sfx_skill_Monokuma_Punishment_Corporal_Preparing",
	FashionAttackAct = "use_skill",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142530</summary>
<pre><code>{
	id = 142530,
	BuffName = "体罚准备（生命流失）",
	BuffRate = { Odds = 100 },
	BuffStateID = 142530,
	BuffEffect = { Hp = { type = 10220 }, type = "HSPChange" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142531</summary>
<pre><code>{
	id = 142531,
	BuffName = "体罚准备（受到火属性伤害提高）",
	BuffRate = { Odds = 100 },
	BuffEffect = { BeFireDamPer = -0.2, type = "AttrChange" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142532</summary>
<pre><code>{
	id = 142532,
	BuffName = "体罚准备（特别体罚）",
	BuffRate = { Odds = 100 },
	Condition = { need_dead = 1, type = "OnNearDeath" },
	BuffStateID = 142532,
	BuffEffect = { Odds = 100, id = { 142455 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142533</summary>
<pre><code>{
	id = 142533,
	BuffName = "体罚准备（绝望斩杀）",
	BuffRate = { Odds = 100 },
	BuffEffect = { Odds = 100, id = { 142534 }, type = "AddBuff" },
}
</code></pre>
</details>

---

### ![skill_4927001][skill_4927001] **Class Trial | 班级审判** #4927
#### **Details**
| | |
|-|-:|
| **Type** | ClassTrial |
| **Max Lv** | 5 |
| **Damage Type** | Physical, HP Loss |
| **Target** | Friend SkillLockedTarget |
| **Range** | 10.0 m |
| **Skill CD** | 30.0 sec |
| **Cast Delay** | 2.0 sec |
| **Skill Cost** | 203 SP |
| | |
#### **Description**
对友方尸体进行班级审判，在5秒内持续控制半径10米内的所有敌人。如果击倒者在半径10米范围内，则立刻将目标牵引至身旁并对其释放一次【特别体罚】。如果时间结束后仍然找不到目标，则对范围内所有敌人造成一次（物理攻击+自身灵巧*自身智力/5）*<b style="color: blue">[3300% / 3600% / 3900% / 4200% / 4500%]</b>的火属性物理伤害以及最大生命值*50%的生命流失，控制效果和生命流失伤害对MVP/Mini魔物无效

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4927005,
	NameZh = "班级审判",
	Level = 5,
	Icon = "skill_4927001",
	Cost = 1,
	Desc = { { id = 4927000, params = { 4500 } } },
	DamageType = 5,
	SkillType = "ClassTrial",
	Camps = "Friend",
	Launch_Range = 10,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 30,
	SkillCost = { sp = 203 },
	DelayCD = 2,
	Logic = "SkillLockedTarget",
	Logic_Param = { ground_skill_id = 4935005, select = 3 },
	AttackAct = { "use_skill4" },
	SE_cast = "Skill/sfx_skill_Monokuma_Trial_Class",
	FashionAttackAct = "use_skill21",
}
</code></pre>
</details>

---

### ![skill_4928001][skill_4928001] **Final Punishment: The Academy Festival of Revelry | 最终体罚：狂欢的学院祭** #4928
#### **Details**
| | |
|-|-:|
| **Type** | MonokumaFinalFestival |
| **Max Lv** | 10 |
| **Damage Type** | Physical |
| **Target** | Enemy SkillSelfRange |
| **Skill CD** | 36.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 600 SP |
| | |
#### **Description**
立刻在自身周围召唤4个【自爆黑白熊】，并使所有黑白熊分身对应的技能效果剩余时间变为5秒，5秒倒计时后，所有黑白熊分身会进行自爆并在大范围内造成(物理攻击+自身灵巧*自身智力/5）*<b style="color: blue">[2700% / 3000% / 3300% / 3600% / 3900% / 4200% / 4500% / 4800% / 5100% / 5400%]</b>火属性物理伤害

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4928010,
	NameZh = "最终体罚：狂欢的学院祭",
	Level = 10,
	Icon = "skill_4928001",
	Cost = 1,
	Desc = { { id = 4928000, params = { 5400 } } },
	DamageType = 1,
	SkillType = "MonokumaFinalFestival",
	Camps = "Enemy",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 36,
	SkillCost = { sp = 600 },
	DelayCD = 1,
	NoTargetAutoCast = 1,
	Logic = "SkillSelfRange",
	Logic_Param = {
		angles = { 0, 90, 180, 270 },
		explode_skill_id = 4934001,
		final_time = 5,
		radius = 4,
		scene_trap_skill_ids = { 4936, 4937, 4938, 4921, 4940 },
		sub_skill_id = 4940010,
		trap_npc_ids = { 580410 },
	},
	Buff = { self = { 142540 } },
	Pvp_buff = { self = { 142540 } },
	AttackAct = { "use_skill5" },
	SE_cast = "Skill/sfx_skill_Monokuma_Carnival",
	FashionAttackAct = "use_skill26",
}
</code></pre>
</details>
<details>
<summary>BUFFER #142540</summary>
<pre><code>{ id = 142540, BuffName = "倒计时", BuffRate = { Odds = 100 }, BuffStateID = 142540 }
</code></pre>
</details>

---

### ![skill_4929001][skill_4929001] **Undisputed authority | 不容置疑的权威** #4929
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
黑白熊受到的物理、魔法伤害减少<b style="color: blue">[12% / 14% / 16% / 18% / 20% / 22% / 24% / 26% / 28% / 30%]</b>，且受到伤害时，有<b style="color: blue">[11% / 12% / 13% / 14% / 15% / 16% / 17% / 18% / 19% / 20%]</b>概率向目标释放【黑白熊炸弹】，这个效果每<b style="color: blue">[1 / 1 / 1 / 1 / 1 / 1 / 1 / 1 / 1 / 1]</b>秒最多触发1次

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4929010,
	NameZh = "不容置疑的权威",
	Level = 10,
	Icon = "skill_4929001",
	Cost = 1,
	Desc = { { id = 4929000, params = { 30, 20, 1 } } },
	Buff = { self = { 142470, 142471 } },
	Pvp_buff = { self = { 142470, 142471 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142470</summary>
<pre><code>{
	id = 142470,
	BuffName = "不容置疑的权威",
	BuffRate = { Odds = 100 },
	BuffEffect = { DamReduc = { a = 0.02, b = 0.1, type = 1 }, MDamReduc = { a = 0.02, b = 0.1, type = 1 }, type = "AttrChange" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142471</summary>
<pre><code>{
	id = 142471,
	BuffName = "不容置疑的权威（受到伤害）",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, buff_skill_can_trigger = 1, must_have_damage = 1, type = "BeAttack" },
	BuffEffect = { IsActive = 0, Odds = 100, effect_cd = 1, id = 4921001, type = "UseSkill" },
}
</code></pre>
</details>

---

### ![skill_4930001][skill_4930001] **Non-existent channel | 不存在的通道** #4930
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
黑白熊总是以神秘的方式出场、退场。陷入濒死状态时，黑白熊钻入地面，进入隐身状态并免疫伤害，并在原地留下一个【装死黑白熊】，持续<b style="color: blue">[3.0 / 3.5 / 4.0 / 4.5 / 5.0]</b>秒。每<b style="color: blue">[50 / 45 / 40 / 35 / 30]</b>秒最多触发1次

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4930005,
	NameZh = "不存在的通道",
	Level = 5,
	Icon = "skill_4930001",
	Cost = 1,
	Desc = { { id = 4930000, params = { 5, 30 } } },
	Buff = { self = { 142484, 142488 } },
	Pvp_buff = { self = { 142484, 142488 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142484</summary>
<pre><code>{
	id = 142484,
	BuffName = "不存在的通道Lv.5",
	BuffRate = { Odds = 100 },
	Condition = { type = "OnNearDeath" },
	BuffEffect = { effect_cd = 30, id = { 142485, 142486, 142487 }, type = "AddBuff" },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142488</summary>
<pre><code>{
	id = 142488,
	BuffName = "不存在的通道地面时间",
	BuffRate = { Odds = 100 },
	BuffEffect = { duration = { a = 0.5, b = 0, type = 1 }, skillID = { 4938 }, type = "AffactSkill" },
}
</code></pre>
</details>

---

### ![skill_4931001][skill_4931001] **Game Organizer (Pseudo) | 游戏组织者（伪）** #4931
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 1 |
| | |
#### **Description**
黑白熊的队友可以获得【绝望的执行者】效果的<b style="color: blue">[50%]</b>加成（不包括特性等级解锁的额外效果），该效果不可叠加且对其他黑白熊无效

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4931001,
	NameZh = "游戏组织者（伪）",
	Level = 1,
	Icon = "skill_4931001",
	Cost = 1,
	Desc = { { id = 4931000, params = { 50 } } },
	Buff = { self = { 142460 } },
	Pvp_buff = { self = { 142460 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142460</summary>
<pre><code>{ id = 142460, BuffName = "游戏组织者（伪）", BuffRate = { Odds = 100 }, ShareTeamBuff = 142461 }
</code></pre>
</details>

---

### ![skill_4932001][skill_4932001] **Corporal Punishment Expert | 体罚达人** #4932
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
黑白熊的各类体罚工具有着惊人的破坏力，黑白熊使用火属性攻击时，元素克制系数+<b style="color: blue">[0.12 / 0.14 / 0.16 / 0.18 / 0.20 / 0.22 / 0.24 / 0.26 / 0.28 / 0.30]</b>，攻击时敌人的铠甲属性等级会降低<b style="color: blue">[1 / 1 / 1 / 1 / 1 / 1 / 1 / 1 / 1 / 1]</b>级，不可叠加（不会低于1级）

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4932010,
	NameZh = "体罚达人",
	Level = 10,
	Icon = "skill_4932001",
	Cost = 1,
	Desc = { { id = 4932000, params = { 0.3, 1 } } },
	Buff = { self = { 142490 } },
	Pvp_buff = { self = { 142490 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #142490</summary>
<pre><code>{
	id = 142490,
	BuffName = "体罚达人",
	BuffRate = { Odds = 100 },
	Condition = { all_skill = 1, need_damage = 1, type = "Attack" },
	BuffEffect = { Odds = 100, id = { 142491, 142492, 142493, 142494, 142495, 142496, 142497, 142498, 142499, 142500 }, type = "AddBuff" },
}
</code></pre>
</details>

---

## **Advanced Runes**

### S-Star Runes

#### 爆弹狂欢·星符文 #379490
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【黑白熊炸弹】伤害＋<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【绝望的执行者】特性等级＋1（生成概率：6%）

#### 羔羊替罪·星符文 #379491
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【替罪羔羊】转移至【装死黑白熊】的伤害比率＋<b style="color:blue">[1% ~ 30%]</b>
- 【绝望的执行者】特性等级＋1（生成概率：6%）

#### 体罚祭典·星符文 #379492
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【最终体罚：狂欢的学院祭】伤害＋<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【绝望的执行者】特性等级＋1（生成概率：6%）

---

### S Runes

#### 体罚预令符文 #379493
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【体罚准备】持续时间增加＋<b style="color:blue">[1.00 ~ 5.00]</b>秒
- 【绝望的执行者】特性等级＋1（生成概率：6%）

#### 鬼影疾行符文 #379494
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【神出鬼没】使黑白熊移动速度＋<b style="color:blue">[1.0% ~ 30.0%]</b>
- 【绝望的执行者】特性等级＋1（生成概率：6%）

#### 校长威仪符文 #379495
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【校长的权威】额外获得<b style="color:blue">[1.0% ~ 30.0%]</b>技能伤害加成
- 【绝望的执行者】特性等级＋1（生成概率：6%）

---

## **Featured Weapon**

---

## **Equipment**

---

## **Aesir Runes**
| Prop Name | Var Name | Value |
| :- | :- | -: |
| Str | Str | 15 |
| Int | Int | 30 |
| Dex | Dex | 25 |
| Luk | Luk | 15 |
| Atk | Atk | 1481.1 |
| Dmg% | AtkPer | 20.0% |
| Def | Def | 190.5 |
| Def% | DefPer | 11.0% |
| M.Def | MDef | 83.3 |
| M.Def% | MDefPer | 12.0% |
| MaxHp | MaxHp | 12177 |
| MaxHp% | MaxHpPer | 10.0% |
| MaxSp | MaxSp | 328 |
| Hit | Hit | 79 |
| Flee | Flee | 65 |
| Crit.Res. | CriRes | 29.7 |
| Refine Atk | Refine | 209.4 |
| Move Spd% | MoveSpdPer | 10.0% |
| Dmg Reduc. | DamReduc | 10.0% |
| Magic Reduc. | MDamReduc | 10.0% |
| Ignore Def | IgnoreDef | 10.0% |
| Phy. Dmg Inc.  | DamIncrease | 10.0% |
| Pen. | DamSpike | 10.0% |
| Fire Dmg | FireAtk | 15.0% |
| Demi-Human Re. | DemiHumanResPer | 10.0% |


[rune_0]: ../img/rune_0.png
[rune_1]: ../img/rune_1.png
[rune_2]: ../img/rune_2.png
[rune_3]: ../img/rune_3.png
[skill_4920001]: ../img/skill_4920001.png
[skill_4921001]: ../img/skill_4921001.png
[skill_4922001]: ../img/skill_4922001.png
[skill_4923001]: ../img/skill_4923001.png
[skill_4924001]: ../img/skill_4924001.png
[skill_4925001]: ../img/skill_4925001.png
[skill_4926001]: ../img/skill_4926001.png
[skill_4927001]: ../img/skill_4927001.png
[skill_4928001]: ../img/skill_4928001.png
[skill_4929001]: ../img/skill_4929001.png
[skill_4930001]: ../img/skill_4930001.png
[skill_4931001]: ../img/skill_4931001.png
[skill_4932001]: ../img/skill_4932001.png
