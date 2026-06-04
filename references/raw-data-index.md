# 原始数据索引

> 加载条件：当 references/ 中的速查表无法满足查询时，加载本文件定位原始 JSON 数据。

## 数据文件

所有原始 JSON 位于 `references/raw-data/` 下。

### dvg_items_sample.json
- **来源**: ro.dvg.cn
- **内容**: 1542 件物品（39个分类，每类前2页）
- **结构**: `[{name, slots, id, category, type, desc, drops, otherSources, effects}]`
- **查询**: 按 `id`、`name`、`category` 字段搜索

### dvg_cards_full.json
- **来源**: ro.dvg.cn
- **内容**: 750 张卡片（约100页数据）
- **结构**: `[{name, equipSlot, id, prefix, attr, drops[{level, monster, rate}], otherSources}]`
- **查询**: 按 `id`、`name`、`equipSlot` 字段搜索

### ginyuki_articles.json
- **来源**: ro.ginyuki.com
- **内容**: 50 篇博客文章标题和URL
- **结构**: `[{title, url}]`
- **用途**: 索引台湾RO社区攻略

### ginyuki_structure.json
- **来源**: ro.ginyuki.com
- **内容**: 18个分类 + 28个关键页面链接
- **结构**: `{categories: [{name, url}], pages: [{name, url}]}`

### ginyuki_terminology.json
- **来源**: ro.ginyuki.com/terminology
- **内容**: 127 条RO术语（已解析到 references/terminology.md）

### ro321_creations.json
- **来源**: ro321.com
- **内容**: 2 条创造/合成配方

### ro321_misc.json
- **来源**: ro321.com
- **内容**: 12 条杂项数据

---

## 搜索策略

1. 优先查 `references/*.md` 速查表
2. 未命中时加载本文件确认数据位置
3. 加载对应 JSON，按 `id` 或 `name` 精确匹配
4. 仍未找到的，标注"数据未收录于本地"

## 数据规模统计

| 数据集 | 收录条数 | 全站估算 |
|--------|---------|---------|
| 物品 | 1,542 | ~17,180 |
| 卡片 | 750 | ~2,540 |
| 魔物 | 0(JS渲染) | ~2,560 |
| 地图 | 0(JS渲染) | ~260 |
| 技能 | 0(JS渲染) | ~320 |
| NPC | 0(JS渲染) | ~1,200 |