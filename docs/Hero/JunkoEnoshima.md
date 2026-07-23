# **江之岛盾子 | 江之岛盾子**

**[ undefined | undefined ]**

undefined

---

## **Update History**
- **[26-05-14] r1581014** - https://www.taptap.cn/moment/803947045760011278
  - Initial release
---

## **Feature Skill**

### ![skill_4950001][skill_4950001] **Ultimate Despair | 超高中级的绝望** #4950
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 7 |
| | |
#### **Description**
每当江之岛盾子累计对一名敌人造成超过其最大生命值<b style="color: blue">[10% / 10% / 10% / 10% / 10% / 10% / 10%]</b>的伤害时，为其添加一层【绝望】，每一层【绝望】使单位受到和造成的伤害增加<b style="color: blue">[5% / 5% / 5% / 5% / 5% / 5% / 5%]</b>，持续<b style="color: blue">[10 / 10 / 10 / 10 / 10 / 10 / 10]</b>秒，上限为<b style="color: blue">[120 / 140 / 160 / 180 / 200 / 220 / 240]</b>层；【绝望】无法被驱散，无法被黑洞清除，每一层的持续时间会单独计算，；每当江之岛盾子阵亡时，会释放【绝望之声】对周围12米的敌人造成魔法攻击*<b style="color: blue">[30% / 30% / 30% / 30% / 30% / 30% / 30%]</b>*目标绝望【层数】的真实魔法伤害；如果此时目标身上的【绝望】层数已经到达上限，会因为无法承受更多的绝望而自我斩杀，对魔物无效

**Lv4** 如果有敌人因为【绝望之声】阵亡，则【绝望之声】会以该敌人为中心再次释放

**Lv7** 江之岛盾子阵亡后，化身为【绝望残骸】；【绝望残骸】继承阵亡前的【绝望】层数，拥有30%的固定移动速度，并且会不断释放【终极惩罚：自我毁灭】，【绝望力场】会跟随【绝望残骸】而不再留在地面，持续30秒或者直到江之岛盾子被原地复活或者离开当前场景

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4950007,
	NameZh = "超高中级的绝望",
	Level = 7,
	Icon = "skill_4950001",
	Cost = 1,
	Desc = { { id = 4950000, params = { 10, 5, 30, 10, 240 } } },
	Buff = { self = { 143060, 143041, 143042, 143072, 143076, 143078, 143044 } },
	Pvp_buff = { self = { 143060, 143041, 143042, 143072, 143076, 143078, 143044 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #143060</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143041</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143042</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143072</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143076</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143078</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143044</summary>
<pre><code>undefined
</code></pre>
</details>

---

## **Skills**

### ![skill_4951001][skill_4951001] **The First Glimpse of Despair | 绝望的初现** #4951
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| **Damage Type** | Magic  |
| **Target** | Enemy SkillPointRange |
| **Range** | 8.0 m |
| **Skill CD** | 2.5 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | <b style="color: blue">105 SP / 120 SP / 135 SP / 150 SP / 165 SP / 180 SP / 195 SP / 210 SP / 225 SP / 240 SP</b> |
| | |
#### **Description**
在目标敌人处生成一道绝望波纹，持续5秒，每秒对范围内敌人造成魔法攻击*<b style="color: blue">[2200% / 2400% / 2600% / 2800% / 3000% / 3200% / 3400% / 3600% / 3800% / 4000%]</b>魔法伤害，伤害半径每秒会增加1米，并减少敌人50%的移动速度，

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4951010,
	NameZh = "绝望的初现",
	Level = 10,
	Icon = "skill_4951001",
	Cost = 1,
	Desc = { { id = 4951000, params = { 4000 } } },
	RollType = 2,
	DamageType = 2,
	SkillType = "Attack",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 2.5,
	SkillCost = { sp = 240 },
	DelayCD = 1.5,
	Logic = "SkillPointRange",
	Logic_Param = {
		duration = 5,
		hit = 5,
		interval = 1,
		isTimeTrap = 1,
		max_range = 7,
		no_select = 1,
		range = 3,
		range_inc_per_tick = 1,
		trap_effect = "sfx_danganjunko_jwdcx_buff_prf,none",
	},
	Damage = { { damChangePer = 40, type = 14953 } },
	DamTime = { type = 1, value = 1 },
	Buff = { enemy = { 143000 }, self = { 143080 } },
	Pvp_buff = { enemy = { 143000 }, self = { 143080 } },
	AttackAct = { "use_skill" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Dawn_Despair",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143000</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143080</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4952001][skill_4952001] **The Spread of Despair | 绝望的蔓延** #4952
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 5 |
| **Target** | Enemy SkillLockedTarget |
| **Range** | 8.0 m |
| **Fixed CD** | <b style="color: blue">29.0 sec / 28.0 sec / 27.0 sec / 26.0 sec / 25.0 sec</b> |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 120 SP |
| | |
#### **Description**
向目标敌人散布更深层的绝望，使其陷入不可免疫和抵抗的【恐惧】状态，持续<b style="color: blue">[3 / 3 / 3 / 3 / 3]</b>秒，如果有敌人靠近目标<b style="color: blue">[3 / 3 / 3 / 3 / 3]</b>米，则同样会陷入【恐惧】状态；3秒后【恐惧】会被清除并为所有受到影响的敌人增加<b style="color: blue">[1 / 1 / 1 / 1 / 1]</b>层【绝望】;冷却时间固定不可减少

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4952005,
	NameZh = "绝望的蔓延",
	Level = 5,
	Icon = "skill_4952001",
	Cost = 1,
	Desc = { { id = 4952000, params = { 3, 3, 1 } } },
	SkillType = "Buff",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 4,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 25,
	FixCD = 1,
	SkillCost = { sp = 120 },
	DelayCD = 1,
	Logic = "SkillLockedTarget",
	Logic_Param = { emit = { effect = "sfx_danganjunko_jwdmy_bullet_prf", speed = 20, type = 1 } },
	Buff = { enemy = { 143010, 143011 }, self = { 143081 } },
	Pvp_buff = { enemy = { 143010, 143011 }, self = { 143081 } },
	AttackAct = { "use_skill2" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Spreading_Despair",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143010</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143011</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143081</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4953001][skill_4953001] **The Whisper of Despair | 绝望的低语** #4953
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 5 |
| **Target** | Enemy SkillLockedTarget |
| **Range** | 8.0 m |
| **Skill CD** | 18.0 sec |
| **Cast Delay** | 1.5 sec |
| **Skill Cost** | 160 SP |
| | |
#### **Description**
用带有暗示的言语蛊惑一名玩家，使其在<b style="color: blue">[6 / 7 / 8 / 9 / 10]</b>秒内攻击时，会攻击到其友方玩家；目标在时间内每击杀一个单位就会获得<b style="color: blue">[1 / 1 / 1 / 1 / 1]</b>层【绝望】，且在PVP/GVG中，造成的击杀会归属于江之岛盾子

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4953005,
	NameZh = "绝望的低语",
	Level = 5,
	Icon = "skill_4953001",
	Cost = 1,
	Desc = { { id = 4953000, params = { 10, 1 } } },
	SkillType = "Buff",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 4,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 18,
	SkillCost = { sp = 160 },
	DelayCD = 1.5,
	Logic = "SkillLockedTarget",
	Buff = { enemy = { 143020, 143021, 143022 }, self = { 143082 } },
	Pvp_buff = { enemy = { 143020, 143021, 143022 }, self = { 143082 } },
	AttackAct = { "use_skill2" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Whisper_Despair",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143020</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143021</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143022</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143082</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4954001][skill_4954001] **A Desperate Ending | 绝望的结局** #4954
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| **Target** | Friend SkillLockedTarget |
| **Range** | 8.0 m |
| **Skill CD** | 20.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | <b style="color: blue">110 SP / 120 SP / 130 SP / 140 SP / 150 SP / 160 SP / 170 SP / 180 SP / 190 SP / 200 SP</b> |
| | |
#### **Description**
为一名队友提供一份虚假的希望，为其添加<b style="color: blue">[30 / 30 / 30 / 30 / 30 / 30 / 30 / 30 / 30 / 30]</b>层【绝望】，并使目标身上【绝望】提供额外<b style="color: blue">[1% / 2% / 2% / 3% / 3% / 4% / 4% / 5% / 5% / 5%]</b>的增伤效果，持续<b style="color: blue">[8.0 / 8.5 / 9.0 / 9.5 / 10.0 / 10.5 / 11.0 / 11.5 / 12.0 / 12.5]</b>秒；持续时间内，目标队友不会受到【绝望】的斩杀效果；该技能对江之岛盾子无效

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4954010,
	NameZh = "绝望的结局",
	Level = 10,
	Icon = "skill_4954001",
	Cost = 1,
	Desc = { { id = 4954000, params = { 5, 30, 12.5 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 8,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 20,
	SkillCost = { sp = 200 },
	DelayCD = 1,
	Logic = "SkillLockedTarget",
	Logic_Param = { CdTimes = 1, emit = { effect = "sfx_danganjunko_jwdjj_bullet_prf", speed = 20, type = 1 }, select = 4, team_first = 1 },
	Buff = { self = { 143083 }, team = { 143030, 143051 } },
	Pvp_buff = { self = { 143083 }, team = { 143030, 143051 } },
	AttackAct = { "use_skill3" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Ending_Despair",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143083</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143030</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143051</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4955001][skill_4955001] **Echoes of Despair | 绝望的回响** #4955
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 1 |
| **Target** | Enemy SkillLockedTarget |
| **Range** | 8.0 m |
| **Fixed CD** | 24.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** |  |
| | |
#### **Description**
当使用了其他【绝望】系列的技能后，该技能会变更为更绝望的版本，会在目标周围<b style="color: blue">[5]</b>米内造成效果，并立刻添加<b style="color: blue">[1]</b>层【绝望】，冷却时间固定不可减少

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4955001,
	NameZh = "绝望的回响",
	Level = 1,
	Icon = "skill_4955001",
	Cost = 1,
	Contidion = { skillid = 4953003 },
	Desc = { { id = 4955000, params = { 5, 1 } } },
	SkillType = "Buff",
	Camps = "Enemy",
	Launch_Range = 8,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 3,
	CD = 24,
	FixCD = 1,
	SkillCost = { sp = 0 },
	DelayCD = 1,
	Logic = "SkillLockedTarget",
	AttackAct = { "use_magic" },
	SE_attack = "Skill/sfx_skill_Junko_Mind_Veil",
}
</code></pre>
</details>

---

### ![skill_4956001][skill_4956001] **Veil of the Mind | 心灵帷幕** #4956
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 5 |
| **Target** | Friend SkillNone |
| **Skill Cost** | 30 SP |
| | |
#### **Description**
开启后，江之岛盾子会进入无法被探查和解除的【隐匿】状态，移动速度增加<b style="color: blue">[30% / 35% / 40% / 45% / 50%]</b>，但无法再对看不见江之岛盾子的玩家添加【绝望】；再次使用技能可以取消【心灵帷幕】状态

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4956005,
	NameZh = "心灵帷幕",
	Level = 5,
	Icon = "skill_4956001",
	Cost = 1,
	Desc = { { id = 4956000, params = { 50 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 0,
	SkillCost = { sp = 30 },
	NoTargetAutoCast = 1,
	Logic = "SkillNone",
	Logic_Param = { no_target = 1 },
	Buff = { self = { 143090, 143091, 143092, 143095 } },
	Pvp_buff = { self = { 143090, 143091, 143092, 143095 } },
	AttackAct = { "use_skill" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Mind_Veil_Start",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143090</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143091</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143092</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143095</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4957001][skill_4957001] **Despair Forcefield | 绝望力场** #4957
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| **Target** | Friend SkillNone |
| **Skill CD** | 15.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | 120 SP |
| | |
#### **Description**
在自身周围生成绝望力场，每秒对范围内敌人造成魔法攻击*<b style="color: blue">[600% / 800% / 1000% / 1200% / 1400% / 1600% / 1800% / 2000% / 2200% / 2400%]</b>魔法伤害，持续10秒，敌人在范围内的时间越久，受到的伤害越高，每停留1秒受到的伤害额外提高5%，且【绝望力场】内敌人自我斩杀的【绝望】层数阈值会降低至5层；如果江之岛盾子在开启【绝望力场】时阵亡，会在地面留下一个更大的力场，持续15秒或者江之岛盾子复活

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4957010,
	NameZh = "绝望力场",
	Level = 10,
	Icon = "skill_4957001",
	Cost = 1,
	Desc = { { id = 4957000, params = { 2400 } } },
	SkillType = "Buff",
	Camps = "Friend",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 15,
	SkillCost = { sp = 120 },
	DelayCD = 1,
	NoTargetAutoCast = 1,
	Logic = "SkillNone",
	Logic_Param = { no_target = 1 },
	Buff = { self = { 143100, 143105, 143109, 143110 } },
	Pvp_buff = { self = { 143100, 143105, 143109, 143110 } },
	AttackAct = { "use_skill5" },
	E_Attack_On = 1,
	SE_attack = "Skill/sfx_skill_Junko_Aura_Despair",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143100</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143105</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143109</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143110</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4958001][skill_4958001] **The Ultimate Punishment: Self-Destruction | 终极惩罚：自我毁灭** #4958
#### **Details**
| | |
|-|-:|
| **Type** | LeadSkill |
| **Max Lv** | 10 |
| **Damage Type** | Magic  |
| **Target** | Enemy SkillSelfRange |
| **Channel Time** | 5.0 sec |
| **Fixed CD** | 30.0 sec |
| **Cast Delay** | 1.0 sec |
| **Skill Cost** | <b style="color: blue">180 SP / 200 SP / 220 SP / 240 SP / 260 SP / 280 SP / 300 SP / 320 SP / 340 SP / 360 SP</b> |
| | |
#### **Description**
江之岛盾子以自我毁灭的方式向敌人施加绝望，每秒释放5个言弹攻击大范围内随机敌人，每个言弹造成魔法攻击*<b style="color: blue">[1200% / 1300% / 1400% / 1500% / 1600% / 1700% / 1800% / 1900% / 2000% / 2100%]</b>的魔法伤害，最多持续5秒，可以随时中断；【终极惩罚：自我毁灭】需要持续施法，时间取决于攻击次数，施法期间江之岛盾子处于无敌状态，【终极惩罚：自我毁灭】结束时，江之岛盾子会自我斩杀并触发【绝望之声】；冷却时间固定不可减少

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4958010,
	NameZh = "终极惩罚：自我毁灭",
	Level = 10,
	Icon = "skill_4958001",
	Cost = 1,
	Desc = { { id = 4958000, params = { 2100 } } },
	RollType = 2,
	DamageType = 2,
	SkillType = "LeadSkill",
	Camps = "Enemy",
	Launch_Range = 0,
	Fire_EP = 3,
	Target_EP = 3,
	Attack_EP = 2,
	CD = 30,
	FixCD = 1,
	SkillCost = { sp = 360 },
	DelayCD = 1,
	NoTargetAutoCast = 1,
	Lead_Type = { DCT = 5, clientinterrupt = 1, type = 4 },
	Logic = "SkillSelfRange",
	Logic_Param = {
		chant_buff = { 143150 },
		dead_call_skill = 1,
		duration = 5,
		fieldarea_cannot_immune = 1,
		interval = 0.2,
		isTimeTrap = 1,
		lead_end_buff = { 143151 },
		lead_skill_count = 25,
		noMoveAction = 1,
		no_select = 1,
		range = 7,
		range_num = 1,
	},
	Damage = { { damChangePer = 21, type = 14953 } },
	DamTime = { type = 1, value = 1 },
	Buff = { self = { 143152 } },
	Pvp_buff = { self = { 143152 } },
	CastAct = "use_skill6",
	E_Attack_On = 1,
	SE_cast = "Skill/sfx_skill_Junko_Self_Destroy",
	FashionCastAct = "reading2",
}
</code></pre>
</details>
<details>
<summary>BUFFER #143152</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4959001][skill_4959001] **Enjoy Despair | 享受绝望** #4959
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
每当江之岛盾子阵亡、击杀敌人或者附近有玩家被【绝望】斩杀时，自身的【绝望】效果会提升<b style="color: blue">[1% / 2% / 3% / 4% / 5% / 6% / 7% / 8% / 9% / 10%]</b>，最多提升<b style="color: blue">[10% / 20% / 30% / 40% / 50% / 60% / 70% / 80% / 90% / 100%]</b>，效果持续<b style="color: blue">[30 / 30 / 30 / 30 / 30 / 30 / 30 / 30 / 30 / 30]</b>秒，会在离开当前地图时清空效果；每当江之岛盾子为其他人添加【绝望】时，为自身添加一层【绝望】

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4959010,
	NameZh = "享受绝望",
	Level = 10,
	Icon = "skill_4959001",
	Cost = 1,
	Desc = { { id = 4959000, params = { 10, 100, 30 } } },
	Buff = { self = { 143181, 143182 } },
	Pvp_buff = { self = { 143181, 143182 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #143181</summary>
<pre><code>undefined
</code></pre>
</details>
<details>
<summary>BUFFER #143182</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4960001][skill_4960001] **Ultimate High School Level Gal | 超高中级的辣妹** #4960
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
江之岛盾子造成伤害时，会使目标的暴击防护减少<b style="color: blue">[10 / 20 / 30 / 40 / 50]</b>，暴伤减免减少<b style="color: blue">[20% / 40% / 60% / 80% / 100%]</b>，持续10秒；江之岛盾子的技能会基于暴击伤害造成额外伤害，等同于(自身的暴伤加成－对方暴伤减免)*<b style="color: blue">[10% / 20% / 30% / 40% / 50%]</b>，至少提升<b style="color: blue">[10% / 20% / 30% / 40% / 50%]</b>

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4960005,
	NameZh = "超高中级的辣妹",
	Level = 5,
	Icon = "skill_4960001",
	Cost = 1,
	Desc = { { id = 4960000, params = { 100, 50, 50, 50 } } },
	Buff = { self = { 143190 } },
	Pvp_buff = { self = { 143190 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #143190</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4961001][skill_4961001] **Masochistic VIT | 受虐体质** #4961
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
江之岛盾子有着超乎常人的生命力量，她有着相比其他冒险者更高的基础生命值，且每一点六维都会增加<b style="color: blue">[2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10 / 10]</b>点生命上限，并获得<b style="color: blue">[5% / 7% / 9% / 11% / 13% / 15% / 17% / 18% / 19% / 20%]</b>的物理反伤和魔法反伤；江之岛盾子可以承受的绝望层数上限增加<b style="color: blue">[1 / 2 / 3 / 4 / 5 / 6 / 7 / 8 / 9 / 10]</b>层

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4961010,
	NameZh = "受虐体质",
	Level = 10,
	Icon = "skill_4961001",
	Cost = 1,
	Desc = { { id = 4961000, params = { 20, 10, 10 } } },
	Buff = { self = { 143201 } },
	Pvp_buff = { self = { 143201 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #143201</summary>
<pre><code>undefined
</code></pre>
</details>

---

### ![skill_4962001][skill_4962001] **Tangible Despair | 具象绝望** #4962
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
江之岛盾子的普通攻击会向目标发射各种言弹对目标造成精神攻击，每个言弹造成魔法攻击*<b style="color: blue">[600% / 700% / 800% / 900% / 1000%]</b>的魔法伤害，每次发射的言弹数量基于攻击速度；【具象绝望】视为技能攻击，无法暴击，且发射间隔固定为<b style="color: blue">[1 / 1 / 1 / 1 / 1]</b>秒

#### **Notes**

#### **Raw Lua**
<details>
<summary>SKILL</summary>
<pre><code>{
	id = 4962005,
	NameZh = "具象绝望",
	Level = 5,
	Icon = "skill_4962001",
	Cost = 1,
	Desc = { { id = 4962000, params = { 1000, 1 } } },
	Buff = { self = { 143200 } },
	Pvp_buff = { self = { 143200 } },
}
</code></pre>
</details>
<details>
<summary>BUFFER #143200</summary>
<pre><code>undefined
</code></pre>
</details>

---

## **Advanced Runes**

### S-Star Runes

#### 初现绝望·星符文 #379496
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【绝望的初现】伤害＋<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

#### 力场崩坏·星符文 #379497
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【绝望力场】自身生命值越低，伤害越高，最多增加<b style="color:blue">[1.0% ~ 100.0%]</b>，阵亡时生命值视为0
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

#### 自毁终罚·星符文 #379498
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【终极惩罚：自我毁灭】对魔物的伤害＋<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

---

### S Runes

#### 蔓延余响符文 #379499
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【绝望的蔓延】持续时间＋<b style="color:blue">[0.10 ~ 2.00]</b>秒
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

#### 结局连锁符文 #379500
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【绝望的结局】现在可以连续使用2次，但冷却时间＋<b style="color:blue">[0.50 ~ NaN]</b>秒
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

#### 心幕侵抗符文 #379501
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【心灵帷幕】开启时，提供<b style="color:blue">[1.0% ~ 30.0%]</b>异常状态攻击和异常状态抵抗
- 【超高中级的绝望】特性等级＋1（生成概率：6%）

---

## **Featured Weapon**

---

## **Equipment**

---

## **Aesir Runes**
| Prop Name | Var Name | Value |
| :- | :- | -: |
| Int | Int | 30 |
| VIT | Vit | 25 |
| Luk | Luk | 20 |
| Def | Def | 160.5 |
| Def% | DefPer | 12.0% |
| M.Atk | MAtk | 1809.5 |
| M.Atk% | MAtkPer | 15.0% |
| M.Def | MDef | 70.1 |
| M.Def% | MDefPer | 12.0% |
| MaxHp | MaxHp | 19511 |
| MaxHp% | MaxHpPer | 10.0% |
| MaxSp | MaxSp | 176 |
| Flee | Flee | 21 |
| Crit.Res. | CriRes | 22.5 |
| Crit.Dmg | CriDamPer | 10.0% |
| Refine M.Atk | MRefine | 229.7 |
| Dmg Reduc. | DamReduc | 12.0% |
| Magic Reduc. | MDamReduc | 12.0% |
| Ignore M.Def | IgnoreMDef | 15.0% |
| M.Dmg Inc. | MDamIncrease | 15.0% |
| M.Pen. | MDamSpike | 15.0% |
| Demi-Human Re. | DemiHumanResPer | 10.0% |


[rune_0]: ../img/rune_0.png
[rune_1]: ../img/rune_1.png
[rune_2]: ../img/rune_2.png
[rune_3]: ../img/rune_3.png
[skill_4950001]: ../img/skill_4950001.png
[skill_4951001]: ../img/skill_4951001.png
[skill_4952001]: ../img/skill_4952001.png
[skill_4953001]: ../img/skill_4953001.png
[skill_4954001]: ../img/skill_4954001.png
[skill_4955001]: ../img/skill_4955001.png
[skill_4956001]: ../img/skill_4956001.png
[skill_4957001]: ../img/skill_4957001.png
[skill_4958001]: ../img/skill_4958001.png
[skill_4959001]: ../img/skill_4959001.png
[skill_4960001]: ../img/skill_4960001.png
[skill_4961001]: ../img/skill_4961001.png
[skill_4962001]: ../img/skill_4962001.png
