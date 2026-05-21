# **Himmelmez | 希默梅斯**

**[ 神使之肆 | 神使之肆 ]**

凡人之生死,不过是女神赐予我的棋子。

---

## **Update History**
- **[26-05-14] r1581014** - https://www.taptap.cn/moment/803947045760011278
  - Initial release
---

## **Feature Skill**

### ![skill_4880001][skill_4880001] **傀儡之主 | 傀儡之主** #4880
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 7 |
| | |
#### **Description**
希默梅斯可以号令深渊中的可怖之物对敌人进行攻击，使用【诏令待出】后，【可怖之物】潜伏在希默梅斯周围进行伏击，每隔1秒对圆环范围内所有敌人造成物理攻击*<b style="color: blue">[2800% / 3200% / 3600% / 4000% / 4400% / 4800% / 5200%]</b>的物理伤害伤害,并强制使其减速<b style="color: blue">[50% / 55% / 60% / 65% / 70% / 75% / 80%]</b>，【可怖之物】的初始伏击半径为8米，圆环的宽度为4米，可以通过【魂沼出渊】更改可怖之物的巡逻半径

**Lv4** 【神诏影从】的持续时间内，可怖之物的碰撞半径增加2米

**Lv7** 仅攻击到一个敌人时，【可怖之物】的伤害增加50%
获得技能【灵魂苏生】：当【可怖之物】击杀、斩杀或者在10秒内累计攻击一名玩家5次后，可与攫取对方的灵魂，持续30秒；希默梅斯可以将灵魂转化为一具傀儡，傀儡会复制目标玩家的所有属性，视为希默梅斯的召唤物，并且会自行进行战斗，持续25秒

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

### **穿刺之刑 | 穿刺之刑** #4881
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| | |
#### **Description**
希默梅斯挥舞魔剑，召唤地狱的骨刺刺穿地表，对目标以及路径上的敌人造成物理攻击*<b style="color: blue">[1540% / 1780% / 2020% / 2260% / 2500% / 2740% / 2980% / 3220% / 3460% / 3700%]</b>的物理伤害，如果目标在【可怖之物】的巡逻范围内，则向目标再次释放【穿刺之刑】，造成相同倍率的物理伤害

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

### **逆权篡令 | 逆权篡令** #4882
#### **Details**
| | |
|-|-:|
| **Type** | HellPlant |
| **Max Lv** | 5 |
| | |
#### **Description**
固定吟唱1.5秒后，展开篡夺权柄的领域，领域半径为8米，靠近领域边缘的敌人会持续受到骨刺的攻击，造成物理攻击*<b style="color: blue">[540% / 720% / 900% / 1080% / 1260%]</b>的物理伤害；试图从领域中离开的敌人会被强制眩晕2.5秒，眩晕效果每15秒最多生效一次。【逆权篡令】会【策反】范围内所有有生命的召唤物，使其攻击其最近的友军，造成希默梅斯的物理攻击*1000%的物理伤害。【可怖之物】无法被【策反】，已经被【策反】的召唤物也无法再被策反；冷却时间固定不可减少

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

### **神使之怒 | 神使之怒** #4883
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
| | |
#### **Description**
希默梅斯向企图靠近她的敌人发动怒火，对其周围5米范围内的敌人造成物理攻击*<b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b>的物理伤害并将他们击退4米，无视霸体效果，并在击退范围内留下持续5秒的骨刺，每秒造成物理攻击*<b style="color: blue">[1700% / 1900% / 2100% / 2300% / 2500% / 2700% / 2900% / 3100% / 3300% / 3500%]</b>的物理伤害

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

### **黄泉引渡 | 黄泉引渡** #4884
#### **Details**
| | |
|-|-:|
| **Type** | Attack |
| **Max Lv** | 10 |
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

### **邪神乐园 | 邪神乐园** #4885
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 5 |
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

### **噬血裁决 | 噬血裁决** #4886
#### **Details**
| | |
|-|-:|
| **Type** | Buff |
| **Max Lv** | 10 |
| | |
#### **Description**
希默梅斯用死者的鲜血强化她的魔刃，获得<b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b>的物理穿刺和忽视物理防御，她的攻击有<b style="color: blue">[3% / 6% / 9% / 12% / 15% / 18% / 21% / 24% / 27% / 30%]</b>使敌人陷入无法免疫的【流血】状态，持续5秒；【噬血裁决】持续600秒，技能持续时间内释放职业技能时额外消耗5%当前生命

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

### **终焉降临 | 终焉降临** #4887
#### **Details**
| | |
|-|-:|
| **Type** | HorribleAddBuff |
| **Max Lv** | 1 |
| | |
#### **Description**
希默梅斯唤醒其体内的死亡之力开启其终极形态，【终焉降临】期间每秒流失自身当前10%的生命，【不灭之躯】的效果翻倍；【终焉降临】会唤醒【可怖之物】，使其展现真实形态，并且每隔0.5秒对碰撞到的敌人造成与【傀儡之主】相同倍率的伤害，持续30秒，冷却时间固定不可减少；持续时间内【可怖之物】获得若干强化效果:
【可怖之物】的碰撞伤害会斩杀血量低于25%的敌人（对魔物无效）
※【可怖之物】击杀或者斩杀敌人时，其所有伤害增加20%，持续10秒，可以叠加
※可以使用神诏影从使【可怖之物】在五秒内停止移动
希默梅斯免疫敌方【可怖之物】的斩杀效果；【终焉降临】需要在【可怖之物】在场时使用，

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

### **邪神加冕 | 邪神加冕** #4888
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
希默梅斯的技能和她的【可怖之物】以及队伍内所有有生命的召唤物造成的伤害提升<b style="color: blue">[10% / 20% / 30% / 40% / 50%]</b>，每当附近12米内有任意有生命的召唤物阵亡时，该效果会对自身提升<b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b>，持续30秒，可以叠加

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

### **泣血回响 | 泣血回响** #4889
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
每当希默梅斯击杀敌人时，恢复自身<b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b>的最大生命，击杀玩家时恢复量提升至<b style="color: blue">[2% / 4% / 6% / 8% / 10% / 12% / 14% / 16% / 18% / 20%]</b>；希默梅斯受到生命流失或者消耗生命释放技能时，周围6米范围内的敌人会受到50%的等额生命流失，自身损失的生命会100%转化为可叠加的护盾，持续15秒，该护盾无法抵挡生命流失伤害

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

### **不灭之躯 | 不灭之躯** #4890
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 5 |
| | |
#### **Description**
希默梅斯每损失10%的血量，便会获得<b style="color: blue">[2% / 4% / 6% / 8% / 10%]</b>的最终伤害减免、技能伤害减免以及普攻伤害减免；每损失1000HP，增加自身<b style="color: blue">[1 / 2 / 3 / 4 / 5]</b>点物理攻击力（PVP/GVG内效果为25%）希默梅斯受到的治疗不会被转移也不会被转换为伤害

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

### **亵神之殇 | 亵神之殇** #4891
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 10 |
| | |
#### **Description**
希默梅斯和【可怖之物】造成伤害时，可以使敌人的物理防御下降<b style="color: blue">[0.5% / 1.0% / 1.5% / 2.0% / 2.5% / 3.0% / 3.5% / 4.0% / 4.5% / 5.0%]</b>，最多叠加10层。目标受到物理伤害时，溢出的忽视物理防御会转化为额外伤害，最多提升50%（暴击等无视物理防御的情形不适用）

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

### **Fallen Angel | 堕落天使** #4892
#### **Details**
| | |
|-|-:|
| **Type** | Passive |
| **Max Lv** | 1 |
| | |
#### **Description**
希默梅斯的种族变为天使，攻击属性强制为不死属性；计算元素克制系数时，不死属性对1级元素铠甲的克制系数变为（2-原克制系数），其他增加元素克制属性的效果会在此之后另外计算

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


[skill_4880001]: data:image/png;base64,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
