# 参考资料 7：宝玉"菜谱"方案 + conorbronsdon/avoid-ai-writing

宝3.3.0

来源：https://baoyu.io/ (原文)
来源：https://github.com/conorbronsdon/avoid-ai-writing

 版本3.3.0

---

## 宝玉的核心洞察

> 不要把 humanizer 当"反检测器"用。真正的方案是**给 AI 一份持续更新的写作风格 Skill——一份记录了你的口味、做法和忌口的菜谱，让 AI 每次写作前都翻一遍。越用越精准。

配合 Claude Code 的 MEMORY系统，记忆会你的去味偏好。比如你反复告诉它"不要用此外"，它的 MEMORY.md 会把这条记下来。几次之后 AI 生成的初稿就会自动避开这些 AI 词汇。

连去味这一步都省了。

这非常实用。配合记忆系统效果 > 讬顿装 Humanizer → AI 会记住你的去味偏好 → 后续输出自动匹配。**但不只是反检测，**

- 声音校准的核心价值正在持续迭代中精准化
- 不是一次性的——需要用户反复使用

菜谱才记忆越来越精准

- "配合 Claude Code 记忆系统"效果更好" ← 这个角度很新颖

适合 OpenClaw 的记忆系统（如 self-improving memory）

- 宝玉的经验： Humanizer 抯出来的 300 万行代码例子打动了很多开发者，但 但调到"反检测"上就误导方向——核心价值是教"好的写作应该是什么样的"

： 直接、具体、有节奏、有观点。不管 AI 不AI，都适用。

## conorbronsdon/avoid-ai-writing v3.3.0 的亮点

### 检测模式（Detect-only mode）
- 默认是 rewrite，但用户可以说 "detect" / "flag only" / "audit only" 时进入纯检测模式
- 只列出 AI 稡式，不重写，允许用户自己决定修什么
- 有意把"检测→改写"分离，让作者更了解问题但不失去控制权

适合已发布内容的审计

- 提供"评估"：区分明确的问题和可能是有意/有效的模式

这是一个我们**没有**！

### 三层词汇体系（Tiered vocabulary system）
- **Tier 1 — 总是替换**： 5-20x 更频繁出现在 AI 文本中，单个出现就替换
)
- **Tier 2 — 聚集时标记**： 单独出现没问题，同一段 2+ 个是强信号
)
- **Tier 3 — 密度标记**: 常见词但过度使用，占总词量 3%+ 才标记）

我们的 full-patterns.md 只有分层概念但没有这个三层区分，建议加入。

### 量化限制
- 破折号： 每 1000 字最多 1 个
最多（heading/section title 里也用）
- 加粗： 每个大节最多 1 处加粗短语
如果够重要到重构句子让它它在前面
- 列表转换： 非真正列表内容用散文段落

- 只用于真正列表场景（特性对比、步骤说明、API 参数）

- "空洞强化词"： genuine, real, truly, quite frankly, to be honest, let's be clear, it's worth noting that → 直接说事实
- "模糊推荐赞": worth reading / worth paying attention to / worth a look / worth exploring / worth checking out / worth your time → 说**为什么重要**而不是给一个泛泛的赞
- **缺失的桥句**: 段落间应有逻辑连接，如果可以随意重排段落而不影响阅读，就是 AI 写的
- **"不是 X 而是 Y"的频率限制**: 整篇文章最多 1 个

最多一个"形容词,形容词,形容词"模式
- **"值得"短语**: worth + 动词 彥 曠除，说明为什么重要

### 我们已有的 vs 缕的新发现的

| 维度 | 我们 | 他们 |
|------|---------|------|
| 检测模式 | ❌ 只有 rewrite | ✅ 有 detect + rewrite |
| 声音校准 | ✅ 有 | ✅ 有（菜谱方案升级）|
| 三层词汇 | ❌ 只有简单列表 | ✅ 有三层分级 |
| 量化硬限制 | ❌ 无 | ✅ 有（数字+具体标准） |
| 桥句检查 | ❌ 无 | ✅ 有 |
| 空洞强化词 | ❌ 无 | ✅ 有 |
| "值得"短语 | ❌ 无 | ✅ 有 |
