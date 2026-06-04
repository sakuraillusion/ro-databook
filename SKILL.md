---
name: ro-databook
description: |
  Comprehensive Ragnarok Online (Gravity original) knowledge base.
  Covers items, cards, monsters, job classes, skills, maps, game mechanics, and terminology.
  Use when the user asks about RO game data, item stats or IDs, card effects, monster drops,
  class skills, map locations, game formulas, RO terminology, or any RO factual query.
  Use when user mentions RO, Ragnarok Online, Poring, Prontera, Baphomet, Geffen, Payon,
  Morroc, or other RO-specific names.
  Strictly limited to the original PC MMORPG - does NOT cover mobile games
  (守护永恒的爱, RO Origin), sequels, or spin-offs.
---

# RO Databook — Ragnarok Online 原作大书库

Ragnarok Online (Gravity 2002) 完整知识库。覆盖物品、卡片、魔物、职业、技能、地图、游戏机制和术语。

## 铁律：仅限原作

本 Skill 只覆盖 **Gravity 原版 Ragnarok Online PC MMORPG**（韩服 kRO / 台服 TwRO / 国际服 iRO / 国服 cRO）。

**绝对不包含**以下内容，如用户问起必须明确拒绝：
- 守护永恒的爱 (RO Mobile) 及其任何版本
- RO Origin / RO 起源
- RO2 (Ragnarok Online 2)
- 任何非 Gravity 原作的衍生游戏、动漫、小说

---

## 查询规则

当用户提出 RO 相关查询时，按以下优先级执行：

1. **先看分类**：确认查询属于哪个领域（物品/卡片/魔物/职业/技能/地图/机制/术语）
2. **查对应 references**：加载对应的 reference 文件获取准确数据
3. **查原始数据**：如 references 中未找到，查 `references/raw-data/` 下的 JSON 数据库
4. **标注数据来源**：回复时标注数据来自哪个文件（如 `[dvg_cards]`、`[ro321]`）
5. **标注不确定性**：跨服数据可能有差异时注明；未收录数据明确说明

---

## 游戏机制速查

### 九属性克制链（4级倍率）

```
   Lv1:125%/90%  Lv2:150%/75%  Lv3:175%/50%  Lv4:200%/25%

   火 → 地 → 风 → 水 → 火    (循环克制)
   圣 ↔ 暗                     (互克)
   火+圣 → 不死                (克制)
   毒 / 念 / 无                (独立体系)
```

### 体型修正（武器伤害倍率）

| 体型 | 短剑 | 单手剑 | 双手剑 | 单手矛 | 双手矛 | 斧 | 钝器 | 弓 | 拳刃 |
|------|------|--------|--------|--------|--------|-----|------|-----|------|
| 小型 | 100% | 75% | 75% | 75% | 75% | 50% | 75% | 100% | 75% |
| 中型 | 75% | 100% | 75% | 75% | 75% | 100% | 100% | 100% | 100% |
| 大型 | 50% | 75% | 100% | 100% | 100% | 100% | 100% | 75% | 75% |

### 十种族

无形 / 不死 / 动物 / 植物 / 昆虫 / 鱼类 / 恶魔 / 人形 / 天使 / 龙族

### 六大基本素质

| 素质 | 主要影响 | 衍生属性 |
|------|---------|---------|
| STR (力量) | 物理ATK、负重 | ATK = BaseATK + 装备ATK × 体型修正 |
| AGI (敏捷) | ASPD、FLEE | FLEE = BaseLv + AGI + 补正 |
| VIT (体力) | MaxHP、DEF、抗性 | DEF = VIT + 装备DEF |
| INT (智力) | MATK、MaxSP、MDEF | MDEF = INT + 装备MDEF |
| DEX (灵巧) | HIT、远程ATK、咏唱 | HIT = BaseLv + DEX + 补正 |
| LUK (幸运) | CRI、完全回避、掉率 | CRI = LUK/3 + 补正 |

---

## 装备系统

| 部位 | 插槽 | 精炼 | 说明 |
|------|------|------|------|
| 头上/头中/头下 | 0-4槽 | 可(+1~+20) | 头饰分上中下三段 |
| 铠甲 | 0-1槽 | 可 | 身体防具 |
| 武器 | 0-4槽 | 可 | 22种武器类型 |
| 盾牌 | 0-1槽 | 可 | 副手防具 |
| 披肩 | 0-1槽 | 可 | 披风类 |
| 鞋子 | 0-1槽 | 可 | 靴子类 |
| 装饰品×2 | 0-1槽 | 不可 | 左右各一 |

**插槽分布**（基于1542件物品统计）：0槽60% / 1槽18% / 2槽14% / 3槽5% / 4槽2%

---

## 卡片系统

- 魔物击杀掉落（0.01%~1%概率），插入装备获得效果
- 插入后装备获得**前缀名**（如"幸运之 + 短剑"）
- 卡片部位：武器27% / 铠甲18% / 饰品11% / 披肩9% / 鞋子8% / 盾牌7% / 头盔7%
- 详细信息见 `references/cards.md`

---

## 职业体系概要

```
初学者 → 一转 → 二转 → 进阶二转(转生) → 三转 → 四转

剑士 → 骑士→骑士领主→符文骑士
     → 十字军→圣殿十字军→皇家卫士

魔法师 → 巫师→超魔导师→大法师
       → 贤者→智者→元素使

服事 → 牧师→神官→大主教
     → 武道家→武术宗师→修罗

弓箭手 → 猎人→神射手→游侠
       → 诗人/舞娘→搞笑艺人/冷艳舞姬→宫廷乐师/漫游舞者

商人 → 铁匠→神工匠→机匠
     → 炼金术士→创造者→基因学者

盗贼 → 刺客→十字刺客→十字切割者
     → 流氓→神行太保→逐影

扩充: 忍者(影狼/胧) | 神枪手(反叛者) | 跆拳(夜巡者) | 超级初学者
```

详细信息见 `references/jobs.md`

---

## 输出模板

### 物品查询

```
**{物品名} [{槽数}]** (ID#{id})
- 类型: {类别} | ATK: {攻击} | 重量: {重量}
- 装备: {职业限定}
- 来源: {掉落/获取方式}
- 描述: {描述}
```

### 卡片查询

```
**{魔物名}卡片** [{装备位置}] (ID#{id})
- 前缀: {前缀之}
- 效果: {属性/效果}
- 掉落: {魔物名} ({掉率})
```

### 魔物查询

```
**{魔物名}** (ID#{id})
- Lv.{等级} | {种族} | {属性}{属性等级} | {体型}
- HP: {hp} | ATK: {atk} | DEF: {def} | MDEF: {mdef}
- BaseEXP: {exp} | JobEXP: {jobExp}
- 掉落: {物品和掉率}
- 出没: {地图}
```

---

## Gotchas

- **版本差异**：同一物品在不同服务器（kRO/TwRO/iRO/cRO）可能有不同属性，回复时注明参考版本
- **译名混乱**：波利=Poring、吉芬=Geffen、夢羅克=Morroc，同一事物在不同语言/服务器有不同译名
- **数据边界**：本 Skill 收录约1542件物品+750张卡片，超出范围的数据标注"未收录于本地数据库"
- **dvg.cn 怪物/地图数据**：dvg.cn 的怪物和地图页使用 JS 渲染，无法直接爬取；来自 dvg 的数据仅限物品和卡片
- **ro321 编码**：ro321 使用 GB2312 编码，跨站比对时注意可能的乱码
- **严格原作范围**：绝对不为衍生游戏提供数据，问即拒绝
- **精英怪 vs MVP**：精英怪掉率通常 1%、MVP 卡<0.01%，切勿混淆

### 反合理化表

| 想法 | 现实 |
|------|------|
| "RO有很多手游版，随便说一个差不多就行" | 绝不！只输出 Gravity 原版 PC 数据 |
| "这个物品我猜大概 ATK 100 左右" | 必须查 references 或 JSON 数据库，不编造 |
| "用户问的波利卡效果我应该能想起来" | 加载 references/cards.md 或查 JSON，不靠记忆 |
| "ID 差不多的物品属性也差不多" | 每个物品必须用精确 ID 查询，不类推 |

---

## References 加载规则

根据查询类型，只加载需要的文件：

| 查询类型 | 加载文件 |
|---------|---------|
| 物品/装备 | `references/items.md`，未命中则查 `references/raw-data-index.md` |
| 卡片 | `references/cards.md`，未命中则查 `references/raw-data-index.md` |
| 魔物 | `references/monsters.md`，未命中则查 `references/raw-data-index.md` |
| 职业/技能 | `references/jobs.md` |
| 地图 | `references/maps.md` |
| 机制/公式 | `references/mechanics.md` |
| 术语 | `references/terminology.md` |
| 术语解释 | `references/terminology.md` |

**规则**：一次最多加载2个 references 文件，避免浪费上下文。核心机制已在 SKILL.md 中。

---

## 数据来源

本 Skill 数据来自三方交叉比对：

| 来源 | 数据类型 | 收录量 |
|------|---------|--------|
| ro.dvg.cn (RO小册子) | 物品/卡片/分类体系 | 1542物品 + 750卡片 |
| ro.ginyuki.com (Ginyuki's RO Note) | 术语/职业/剧情/任务 | 127术语 + 50文章索引 |
| ro321.com | 创造系统/杂项数据 | 创造配方 + 杂项 |
| ro-encyclopedia-perspective skill | 世界观/地图/角色设定 | 基础知识 |

原始 JSON 数据库位于 `references/raw-data/`，可通过 `references/raw-data-index.md` 索引。

---

## 快速问答

**常见问题可直接凭 SKILL.md 回答的**：属性克制关系、素质公式、体型修正、职业树概要、装备部位/插槽系统、术语解释、地图速览。

**必须加载 references 的**：具体物品属性/ID、卡片效果/掉率、魔物详细数据、技能详情、完整地图列表。