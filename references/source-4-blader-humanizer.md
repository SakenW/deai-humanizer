# 参考资料 4：blader/humanizer（GitHub）

来源：https://github.com/blader/humanizer
版本：v2.5.1，29 种 AI 模式
协议：MIT

---

## 核心差异化特性（我们目前没有的）

### 1. 声音校准（Voice Calibration）

用户可以提供自己的写作样本，技能分析后按用户风格改写：
- 句子长度模式（短促有力？长而流畅？混合？）
- 词汇层次（口语？学术？中间态？）
- 段落开头方式（直接切入？先铺背景？）
- 标点习惯（大量破折号？括号插入？分号？）
- 口头禅或用词偏好
- 过渡方式（显式连接词？直接跳下一个点？）

### 2. 二次审查机制

改写完成后执行：
1. 提问："下面的内容有什么地方一看就是 AI 写的？"
2. 简要回答剩余的 AI 痕迹
3. 提问："现在让它不再明显是 AI 生成的。"
4. 进行二次修订

### 3. 额外模式（我们 24 种中没有的）

| # | 模式 | 说明 |
|---|------|------|
| 13 | 被动语态/无主语句 | "No configuration file needed" → "You do not need a configuration file" |
| 15 | 加粗滥用 | AI 机械地用加粗强调 |
| 16 | 内联标题列表 | "**Performance:** Performance improved..." → 改为正文 |
| 17 | 标题大小写 | "Strategic Negotiations And Partnerships" → "Strategic negotiations and partnerships" |
| 18 | Emoji 滥用 | "🚀 Launch Phase: 💡 Key Insight:" → 删除 emoji |
| 19 | 弯引号 | 用直引号替代 |
| 20 | 聊天机器人残留 | "I hope this helps!" → 删除 |
| 21 | 截断免责声明 | "While details are limited..." → 找来源或删除 |
| 22 | 谄媚语气 | "Great question!" → 直接回应 |
| 25 | 连字符词对 | "cross-functional, data-driven" → 去掉连字符 |
| 26 | 说服性权威套路 | "At its core, what matters is..." → 直接说 |
| 27 | 路标性预告 | "Let's dive in", "Here's what you need to know" → 直接开始 |
| 28 | 碎片化标题 | "## Performance" + "Speed matters." → 让标题自说明 |
| 11 | 同义词循环 | "protagonist...main character...central figure" → 重复用最清晰的那个 |
| 12 | 虚假范围 | "from the Big Bang to dark matter" → 直接列出话题 |

---

## PERSONALITY AND SOUL（与我们的"注入灵魂"高度一致）

基本理念和我们的内容一致：
- 有观点
- 变化节奏
- 承认复杂性
- 用"我"
- 允许混乱
- 对感受具体化

示例对比也相同（300 万行代码那个例子）。
