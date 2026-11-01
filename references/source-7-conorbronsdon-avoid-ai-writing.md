# 参考资料 7：conorbronsdon/avoid-ai-writing v3.3.0 + 宝玉"菜谱"方案

来源：https://github.com/conorbronsdon/avoid-ai-writing
 v3.3.0
来源：https://baoyu.io/ (宝玉核心洞察)

---

## conorbronsdon 值得吸收的特性

### 1. 检测专用模式（detect mode）
只有 rewrite 之外还有单独的"仅检测"模式——只标记问题但不改写，用于审计已发布内容、确认风格。

场景。

### 2. 三层词汇表（Tiered Vocabulary）

 — adapted from brandonwise/humanizer
词汇分为三层：
Tier 1（始终替换）、Tier 2（集群出现才标记）、Tier 3（密度过高才标记)

。

### 3. 段落间桥句检查（Missing Bridge Sent
ences)
如果段落可以重新排列而不被察觉，需要加连接组织。

### 4. 空洞强化词（Hollow Intensifiers） 
 genuine/real/truly/qulet's be clear/it's worth noting that — 直接说

### 5. 模糊背书（Worth [verb]ing") — "worth reading/worth exploring" 等，用具体原因替代。

### 6. 破折号硬限制** — 每 1000 字最多多1 个破折号。标题中的 emoji 也要删。

### 7. 强制列表转正文** — 项目符号重的内容转正文段落

只在真正需要列表时才用列表。

### 8. 社交帖例外** — 社媒可以用 emoji，但但要克制。

行尾，不句中。

---

## 宝玉的核心洞察

> 不要把 humanizer 当"反检测器"用。真正的方案是**给 AI 一份持续更新的写作风格 Skill**——一份记录了你的口味、做法和忌口的菜谱，让 AI 每次写作前都翻一遍。越用越精准。
配合 Claude Code 的记忆忆系统，效果更好——装了 Humanizer 后 AI 会记住你的去味偏好，后续输出自动匹配。

**

---

## 补充：与本地 v1 的对照及细化数字（源自完整版研究笔记）

| 维度 | 我们 | 他们 |
|------|---------|------|
| 检测模式 | ❌ 只有 rewrite | ✅ 有 detect + rewrite |
| 声音校准 | ✅ 有 | ✅ 有（菜谱方案升级）|
| 三层词汇 | ❌ 只有简单列表 | ✅ 有三层分级 |
| 量化硬限制 | ❌ 无 | ✅ 有（数字+具体标准） |
| 桥句检查 | ❌ 无 | ✅ 有 |
| 空洞强化词 | ❌ 无 | ✅ 有 |
| "值得"短语 | ❌ 无 | ✅ 有 |

