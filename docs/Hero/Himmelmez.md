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
Himmelmez 可以号令深渊中的 The Terrifying Thing 对敌人进行攻击，使用【Command Ready】后，【The Terrifying Thing】潜伏在 Himmelmez 周围进行伏击，每隔1秒对圆环范围内所有敌人造成物理攻击*<b style="color: blue">[2800% / 3200% / 3600% / 4000% / 4400% / 4800% / 5200%]</b>的物理伤害伤害,并强制使其减速<b style="color: blue">[50% / 55% / 60% / 65% / 70% / 75% / 80%]</b>，【The Terrifying Thing】的初始伏击半径为8米，圆环的宽度为4米，可以通过【Abyssal Emerge】更改 The Terrifying Thing 的巡逻半径

**Lv4** 【Command, Shadow Follow】的持续时间内，The Terrifying Thing 的碰撞半径增加2米

**Lv7** 仅攻击到一个敌人时，【The Terrifying Thing】的伤害增加50%

获得技能【Soul Revive】：当【The Terrifying Thing】击杀、斩杀或者在10秒内累计攻击一名玩家5次后，可与攫取对方的灵魂，持续30秒；Himmelmez 可以将灵魂转化为一具傀儡，傀儡会复制目标玩家的所有属性，视为 Himmelmez 的召唤物，并且会自行进行战斗，持续25秒

#### **Notes**
#### **Raw Lua**
<details>
<summary>&lt;expand&gt;</summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142160,
      "1": 142161,
      "2": 142162,
      "3": 142210,
      "4": 142192
    }
  },
  "Cost": 1,
  "DamageType": 1,
  "Desc": {
    "0": {
      "id": 4880000,
      "params": {
        "0": 5200,
        "1": 80
      }
    }
  },
  "Icon": "skill_4880001",
  "Level": 7,
  "Logic": "SkillNone",
  "NameZh": "傀儡之主",
  "Pvp_buff": {
    "self": {
      "0": 142160,
      "1": 142161,
      "2": 142162,
      "3": 142210,
      "4": 142192
    }
  },
  "SkillType": "Passive",
  "id": 4880007
}</code></pre>
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
Himmelmez 挥舞魔剑，召唤地狱的骨刺刺穿地表，对目标以及路径上的敌人造成物理攻击*<b style="color: blue">[1540% / 1780% / 2020% / 2260% / 2500% / 2740% / 2980% / 3220% / 3460% / 3700%]</b>的物理伤害，如果目标在【The Terrifying Thing】的巡逻范围内，则向目标再次释放【Piercing Judgment】，造成相同倍率的物理伤害

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill"
  },
  "Attack_EP": 2,
  "Buff": {
    "enemy": {
      "0": 142030
    }
  },
  "CD": 3,
  "Camps": "Enemy",
  "CastAct": "reading",
  "Cost": 1,
  "DamTime": {
    "type": 1,
    "value": 1
  },
  "Damage": {
    "0": {
      "damChangePer": 37,
      "elementparam": 9,
      "type": 83501
    }
  },
  "DamageType": 1,
  "DelayCD": 1.5,
  "Desc": {
    "0": {
      "id": 4881000,
      "params": {
        "0": 3700
      }
    }
  },
  "Fire_EP": 2,
  "Icon": "skill_4881001",
  "Launch_Range": 7.5,
  "Level": 10,
  "Logic": "SkillTargetRect",
  "Logic_Param": {
    "distance": 8,
    "emit": {
      "effect_logic": {
        "effect": "sfx_himemmeth_kszw_floor_prf",
        "interval": 0.01,
        "random_axis_y": true,
        "type": 1
      },
      "speed": 30,
      "type": 1
    },
    "no_select": 1,
    "range_num": 10,
    "width": 3
  },
  "NameZh": "穿刺之刑",
  "Pvp_buff": {
    "enemy": {
      "0": 142030
    }
  },
  "RollType": 1,
  "SE_attack": "Skill/sfx_skill_Himelmez_impale",
  "SkillCost": {
    "hp": 4800
  },
  "SkillType": "Attack",
  "Target_EP": 2,
  "id": 4881010
}</code></pre>
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
固定吟唱1.5秒后，展开篡夺权柄的领域，领域半径为8米，靠近领域边缘的敌人会持续受到骨刺的攻击，造成物理攻击*<b style="color: blue">[540% / 720% / 900% / 1080% / 1260%]</b>的物理伤害；试图从领域中离开的敌人会被强制眩晕2.5秒，眩晕效果每15秒最多生效一次。【Rebel Mandate】会【策反】范围内所有有生命的召唤物，使其攻击其最近的友军，造成 Himmelmez 的物理攻击*1000%的物理伤害。【The Terrifying Thing】无法被【策反】，已经被【策反】的召唤物也无法再被策反；冷却时间固定不可减少

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill3"
  },
  "Attack_EP": 2,
  "CD": 30,
  "Camps": "Enemy",
  "CastAct": "reading",
  "Cost": 1,
  "DamageType": 1,
  "DelayCD": 1,
  "Desc": {
    "0": {
      "id": 4882000,
      "params": {
        "0": 1260
      }
    }
  },
  "Fire_EP": 3,
  "FixCD": 1,
  "Icon": "skill_4882001",
  "Lead_Type": {
    "CCT": 1.5,
    "type": 2
  },
  "Level": 5,
  "Logic": "SkillSelfRange",
  "Logic_Param": {
    "duration": 15,
    "fieldarea_cannot_immune": 1,
    "hit": 50,
    "interval": 0.3,
    "interval_skills": {
      "0": 4907005,
      "1": 4908005
    },
    "isNpcTrap": 1,
    "isTimeTrap": 1,
    "lastTime": 15,
    "max_count": 1,
    "no_select": 1,
    "npcid": 1729,
    "range": 8
  },
  "NameZh": "逆权篡令",
  "SE_attack": "Skill/sfx_skill_Himelmez_usurp",
  "SkillCost": {
    "hp": 5000
  },
  "SkillType": "HellPlant",
  "Target_EP": 2,
  "id": 4882005
}</code></pre>
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
Himmelmez 向企图靠近她的敌人发动怒火，对其周围5米范围内的敌人造成物理攻击*<b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b>的物理伤害并将他们击退4米，无视霸体效果，并在击退范围内留下持续5秒的骨刺，每秒造成物理攻击*<b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b>的物理伤害

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill4"
  },
  "Attack_EP": 2,
  "CD": 12,
  "Camps": "Enemy",
  "CastAct": "reading",
  "Cost": 1,
  "DamTime": {
    "type": 1,
    "value": 1
  },
  "Damage": {
    "0": {
      "damChangePer": 35,
      "elementparam": 9,
      "type": 83501
    }
  },
  "DamageType": 1,
  "DelayCD": 2,
  "Desc": {
    "0": {
      "id": 4883000,
      "params": {
        "0": 3500,
        "1": 3500
      }
    }
  },
  "Fire_EP": 3,
  "HitEffects": {
    "0": {
      "direction": "back",
      "distance": 4,
      "ignore_no_hit_back": 1,
      "only_first_hitback": 1,
      "speed": 20,
      "type": 1
    }
  },
  "Icon": "skill_4883001",
  "Launch_Range": 4,
  "Lead_Type": {
    "CCT": 0.8,
    "FCT": 4,
    "type": 2
  },
  "Level": 10,
  "Logic": "SkillSelfRange",
  "Logic_Param": {
    "count": 10,
    "fieldarea_cannot_immune": 1,
    "interval": 0.5,
    "isCountTrap": 1,
    "max_count": 1,
    "no_select": 1,
    "range": 4,
    "trap_effect": "sfx_himemmeth_nszn_prf,LowRange_B",
    "whitelist": 1
  },
  "NameZh": "神使之怒",
  "RollType": 1,
  "SE_attack": "Skill/sfx_skill_Himelmez_wrath",
  "SkillCost": {
    "hp": 6000
  },
  "SkillType": "Attack",
  "Target_EP": 2,
  "id": 4883010
}</code></pre>
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
在指定区域打开死亡之门，丧尸之手从地下伸出，对范围内敌人造成每秒造成物理攻击*<b style="color: blue">[800% / 900% / 1000% / 1100% / 1200% / 1300% / 1400% / 1500% / 1600% / 1700%]</b>的物理伤害，持续5秒，并使其【定身】1秒，如果目标抵抗【定身】，则强制降低其80%移动速度，

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill5"
  },
  "Attack_EP": 2,
  "Buff": {
    "enemy": {
      "0": 142130
    }
  },
  "CD": 15,
  "Camps": "Enemy",
  "CastAct": "reading",
  "Cost": 1,
  "DamTime": {
    "type": 1,
    "value": 1
  },
  "Damage": {
    "0": {
      "damChangePer": 17,
      "elementparam": 9,
      "type": 83501
    }
  },
  "DamageType": 1,
  "DelayCD": 2,
  "Desc": {
    "0": {
      "id": 4884000,
      "params": {
        "0": 1700
      }
    }
  },
  "Fire_EP": 3,
  "Icon": "skill_4884001",
  "Launch_Range": 9,
  "Lead_Type": {
    "FCT": 3,
    "type": 2
  },
  "Level": 10,
  "Logic": "SkillPointRange",
  "Logic_Param": {
    "count": 5,
    "duration": 5,
    "interval": 1,
    "isCountTrap": 1,
    "max_count": 1,
    "no_select": 1,
    "range": 3,
    "range_num": 10,
    "trap_effect": "sfx_himemmeth_hqzw_prf,LowRange_B"
  },
  "NameZh": "黄泉引渡",
  "Pvp_buff": {
    "enemy": {
      "0": 142130
    }
  },
  "RollType": 1,
  "SE_attack": "Skill/sfx_skill_Himelmez_ferry",
  "SkillCost": {
    "hp": 3000
  },
  "SkillType": "Attack",
  "Target_EP": 2,
  "id": 4884010
}</code></pre>
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
创造死亡领域，目标范围半径5米内的所有玩家和召唤物不会死亡，持续<b style="color: blue">[6 / 7 / 8 / 9 / 10]</b>秒，范围内所有敌人的护盾效果（护盾数值）会在持续时间内暂时失效，冷却时间固定不可减少

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill3"
  },
  "Attack_EP": 2,
  "Buff": {
    "enemy": {
      "0": 142060,
      "1": 142061,
      "2": 142062
    },
    "friend": {
      "0": 142061
    },
    "self_skill": {
      "0": 142061
    },
    "team": {
      "0": 142061
    }
  },
  "CD": 28,
  "Camps": "Friend|Enemy",
  "CastAct": "reading",
  "Cost": 1,
  "DelayCD": 2,
  "Desc": {
    "0": {
      "id": 4885000,
      "params": {
        "0": 10
      }
    }
  },
  "Fire_EP": 3,
  "FixCD": 1,
  "Icon": "skill_4885001",
  "Launch_Range": 7,
  "Lead_Type": {
    "FCT": 3,
    "type": 2
  },
  "Level": 5,
  "Logic": "SkillSelfRange",
  "Logic_Param": {
    "count": 10,
    "fieldarea_cannot_immune": 1,
    "interval": 1,
    "isCountTrap": 1,
    "max_count": 1,
    "no_select": 1,
    "range": 5,
    "trap_effect": "sfx_himemmeth_wsdly_prf,LowRange_B",
    "whitelist": 1
  },
  "NameZh": "邪神乐园",
  "Pvp_buff": {
    "enemy": {
      "0": 142060,
      "1": 142061,
      "2": 142062
    },
    "friend": {
      "0": 142061
    },
    "self_skill": {
      "0": 142061
    },
    "team": {
      "0": 142061
    }
  },
  "SE_attack": "Skill/sfx_skill_Himelmez_pandemonium",
  "SkillCost": {
    "hp": 8000
  },
  "SkillType": "Buff",
  "Target_EP": 2,
  "id": 4885005
}</code></pre>
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
Himmelmez 用死者的鲜血强化她的魔刃，获得<b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b>的物理穿刺和忽视物理防御，她的攻击有<b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b>使敌人陷入无法免疫的【流血】状态，持续5秒；【Blood Decree】持续600秒，技能持续时间内释放职业技能时额外消耗5%当前生命

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill6"
  },
  "Attack_EP": 2,
  "AutoCondition": {
    "0": {
      "no_target": 1,
      "time": 600,
      "type": 1
    }
  },
  "Buff": {
    "self": {
      "0": 142070,
      "1": 142071,
      "2": 142074,
      "3": 142075
    }
  },
  "CD": 15,
  "Camps": "Friend",
  "CastAct": "reading",
  "Cost": 1,
  "DelayCD": 2,
  "Desc": {
    "0": {
      "id": 4886000,
      "params": {
        "0": 30,
        "1": 30
      }
    }
  },
  "Fire_EP": 3,
  "Icon": "skill_4886001",
  "Lead_Type": {
    "FCT": 3,
    "type": 2
  },
  "Level": 10,
  "Logic": "SkillNone",
  "NameZh": "噬血裁决",
  "Pvp_buff": {
    "self": {
      "0": 142070,
      "1": 142071,
      "2": 142074,
      "3": 142075
    }
  },
  "SE_attack": "Skill/sfx_skill_Himelmez_condemn",
  "SkillCost": {
    "hp": 10000
  },
  "SkillType": "Buff",
  "Target_EP": 2,
  "id": 4886010
}</code></pre>
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
Himmelmez 唤醒其体内的死亡之力开启其终极形态，【Descent of the End】期间每秒流失自身当前10%的生命，【Immortal Body】的效果翻倍；【Descent of the End】会唤醒【The Terrifying Thing】，使其展现真实形态，并且每隔0.5秒对碰撞到的敌人造成与【Master of Puppetry】相同倍率的伤害，持续30秒，冷却时间固定不可减少；持续时间内【The Terrifying Thing】获得若干强化效果:

【The Terrifying Thing】的碰撞伤害会斩杀血量低于25%的敌人（对魔物无效）

※【The Terrifying Thing】击杀或者斩杀敌人时，其所有伤害增加20%，持续10秒，可以叠加

※可以使用Command, Shadow Follow使【The Terrifying Thing】在五秒内停止移动 

Himmelmez 免疫敌方【The Terrifying Thing】的斩杀效果；【Descent of the End】需要在【The Terrifying Thing】在场时使用，

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "AttackAct": {
    "0": "use_skill7"
  },
  "Attack_EP": 2,
  "Buff": {
    "self": {
      "0": 142140,
      "1": 142141,
      "2": 142153
    }
  },
  "CD": 75,
  "Camps": "Friend",
  "CastAct": "reading",
  "Contidion": {
    "skillid": 4883003
  },
  "Cost": 1,
  "DelayCD": 2,
  "Desc": {
    "0": {
      "id": 4887000
    }
  },
  "Fire_EP": 3,
  "FixCD": 1,
  "Icon": "skill_4887001",
  "Lead_Type": {
    "FCT": 3,
    "type": 2
  },
  "Level": 1,
  "Logic": "SkillNone",
  "Logic_Param": {
    "buffIDs": {
      "0": 142145,
      "1": 142146,
      "2": 142252
    }
  },
  "NameZh": "终焉降临",
  "PreCondition": {
    "0": {
      "buffid": 142002,
      "type": 12
    }
  },
  "Pvp_buff": {
    "self": {
      "0": 142140,
      "1": 142141,
      "2": 142153
    }
  },
  "SE_attack": "Skill/sfx_skill_Himelmez_advent",
  "SkillCost": {
    "hp": 12000
  },
  "SkillType": "HorribleAddBuff",
  "Target_EP": 2,
  "id": 4887001
}</code></pre>
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
Himmelmez 的技能和她的【The Terrifying Thing】以及队伍内所有有生命的召唤物造成的伤害提升<b style="color: blue">[10% / 20% / 30% / 40% / 50%]</b>，每当附近12米内有任意有生命的召唤物阵亡时，该效果会对自身提升<b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b>，持续30秒，可以叠加

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142100
    }
  },
  "Cost": 1,
  "Desc": {
    "0": {
      "id": 4888000,
      "params": {
        "0": 50,
        "1": 10
      }
    }
  },
  "Icon": "skill_4888001",
  "Level": 5,
  "NameZh": "邪神加冕",
  "Pvp_buff": {
    "self": {
      "0": 142100
    }
  },
  "SkillType": "Passive",
  "id": 4888005
}</code></pre>
</details>

---

### ![skill_4889001][skill_4889001] **Blood Echo | 泣血回响** #4889
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
每当 Himmelmez 击杀敌人时，恢复自身<b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b>的最大生命，击杀玩家时恢复量提升至<b style="color: blue">[2% / 4% / 6% / 8% / 10% / 12% / 14% / 16% / 18% / 20%]</b>；Himmelmez 受到生命流失或者消耗生命释放技能时，周围6米范围内的敌人会受到50%的等额生命流失，自身损失的生命会100%转化为可叠加的护盾，持续15秒，该护盾无法抵挡生命流失伤害

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142080,
      "1": 142090,
      "2": 142110,
      "3": 142112,
      "4": 142114
    }
  },
  "Cost": 1,
  "Desc": {
    "0": {
      "id": 4889000,
      "params": {
        "0": 5,
        "1": 20
      }
    }
  },
  "Icon": "skill_4889001",
  "Level": 10,
  "NameZh": "泣血回响",
  "Pvp_buff": {
    "self": {
      "0": 142080,
      "1": 142090,
      "2": 142110,
      "3": 142112,
      "4": 142114
    }
  },
  "SkillType": "Passive",
  "id": 4889010
}</code></pre>
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
Himmelmez 每损失10%的血量，便会获得<b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b>的最终伤害减免、技能伤害减免以及普攻伤害减免；每损失1000HP，增加自身<b style="color: blue">[1 / 2 / 3 / 4 / 5]</b>点物理攻击力（PVP/GVG内效果为25%）Himmelmez 受到的治疗不会被转移也不会被转换为伤害

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142120,
      "1": 142122
    }
  },
  "Cost": 1,
  "Desc": {
    "0": {
      "id": 4890000,
      "params": {
        "0": 10,
        "1": 5
      }
    }
  },
  "Icon": "skill_4890001",
  "Level": 5,
  "NameZh": "不灭之躯",
  "Pvp_buff": {
    "self": {
      "0": 142120,
      "1": 142122
    }
  },
  "SkillType": "Passive",
  "id": 4890005
}</code></pre>
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
Himmelmez 和【The Terrifying Thing】造成伤害时，可以使敌人的物理防御下降<b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b>，最多叠加10层。目标受到物理伤害时，溢出的忽视物理防御会转化为额外伤害，最多提升50%（暴击等无视物理防御的情形不适用）

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142190
    }
  },
  "Cost": 1,
  "Desc": {
    "0": {
      "id": 4891000,
      "params": {
        "0": 5
      }
    }
  },
  "Icon": "skill_4891001",
  "Level": 10,
  "NameZh": "亵神之殇",
  "Pvp_buff": {
    "self": {
      "0": 142190
    }
  },
  "SkillType": "Passive",
  "id": 4891010
}</code></pre>
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
Himmelmez 的种族变为天使，攻击属性强制为不死属性；计算元素克制系数时，不死属性对1级元素铠甲的克制系数变为（2-原克制系数），其他增加元素克制属性的效果会在此之后另外计算

#### **Notes**
<details>
<summary style="font-size: 14px;"><b>Raw Lua</b></summary>
<pre><code>{
  "Buff": {
    "self": {
      "0": 142180
    }
  },
  "Contidion": {
    "skillid": 4886003
  },
  "Cost": 1,
  "Desc": {
    "0": {
      "id": 4892000
    }
  },
  "Icon": "skill_4892001",
  "Level": 1,
  "NameZh": {
    "EN": "Fallen Angel",
    "ID": "Fallen Angel",
    "JP": "フォーリンエンジェル",
    "KR": "폴른 엔젤",
    "TH": "Fallen Angel",
    "ZH": "堕落天使",
    "ZHTW": "墮落天使",
    "src": "堕落天使"
  },
  "Pvp_buff": {
    "self": {
      "0": 142180
    }
  },
  "SkillType": "Passive",
  "id": 4892001
}</code></pre>
</details>

---

## **Advanced Runes**

### S-Star Runes

#### Piercing Mark - Star Rune | 穿刺之印·星符文 #379484
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Piercing Judgment】伤害＋<b style="color:blue">[1.0% ~ 60.0%]</b>
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

#### Mark of the End - Star Rune | 终焉之印·星符文 #379485
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- The Terrifying Thing 重复命中敌人时，伤害＋<b style="color:blue">[1% ~ 20%]</b>，至多叠加3次
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

#### Nether Mark - Star Rune | 黄泉之印·星符文 #379486
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Blood Decree】添加的【流血】使敌人受到的治疗效果<b style="color:blue">[1.0% ~ 30.0%]</b>
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

---

### S Runes

#### Divine Envoy Mark Rune | 神使之印符文 #379487
<span> ![Def][rune_2]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Divine Retribution】冷却时间<b style="color:blue">[1% ~ 20%]</b>
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

#### Mark of the Evil God Rune | 邪神之印符文 #379488
<span> ![Buff][rune_3]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Evil God's Domain】范围内敌方玩家最大生命值<b style="color:blue">[1.0% ~ 20.0%]</b>
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

#### Rebel Mandate's Mark Rune 逆权之印符文 #379489
<span> ![Atk][rune_1]  ![Buff][rune_3]  ![Any][rune_0] </span>
- 【Rebel Mandate】领域边缘的骨刺伤害＋<b style="color:blue">[1.0% ~ 50.0%]</b>
- 【Master of Puppetry】特性等级＋1（生成概率：6%）

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
