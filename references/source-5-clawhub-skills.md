# 参考资料 5：ClawHub 上的其他 Humanize 技能

---

## 5a. Humanize Chinese（swaylq/humanize-chinese）

来源：https://clawhub.ai/swaylq/humanize-chinese

### 核心特性
- **中文专用**，16 种检测模式
- **6 种风格转换**：口语风、知乎风、小红书风、微信风、学术风、文艺风
- 带本地 Python 脚本（n-gram 频率表 + patterns_cn.json）
- 支持"学术降重"场景（知网/维普/万方）

### 差异化价值
- **平台风格适配**是我们没有的：不同平台（知乎 vs 小红书 vs 微信）有不同的"人味"标准
- n-gram 统计方法可以作为检测补充（不仅靠规则匹配）

### 注意
- 学术降重/绕过 AIGC 检测的定位有伦理风险
- 需要本地 Python 执行

---

## 5b. AI Humanizer 2.1.0（hades4501/ai-humanizer-2-1-0）

来源：https://clawhub.ai/hades4501/ai-humanizer-2-1-0

### 核心特性
- **24 种模式检测器** + 统计引擎 + CLI
- Node.js 实现，可命令行调用
- 纯本地运行，无外部依赖

### 差异化价值
- 有代码实现的检测器，不仅是指令型
- 可编程集成

---

## 5c. brandonwise/ai-humanizer

来源：https://clawhub.ai/brandonwise/ai-humanizer

### 核心特性
- 24 种模式 + 词汇表 + 统计引擎
- Node.js 实现
- 纯本地，无凭证需求

### 差异化价值
- 与 hades4501 类似，有代码实现
- 增加了 AI 文本评分功能

---

## 5d. moltbro/humanize-ai-text

来源：https://clawhub.ai/moltbro/humanize-ai-text

### 注意
- 安全扫描标记为：明确目的是帮助用户规避 AI/抄袭检测器
- 伦理和潜在法律风险（学术不端、合同/条款违规）
- **不建议作为参考源**

---

## 5e. artur-zhdan/humanize

来源：https://clawhub.ai/artur-zhdan/humanize

- 检测 AI 痕迹并修复（夸大象征、宣传语言、破折号滥用、AI 词汇、谄媚语气）
- 纯指令型
- 与我们现有内容高度重叠

---

## 5f. jz-humanizer

来源：https://clawhub.ai/skills/jz-humanizer

- 基于 Wikipedia AI 写作特征
- 与 blader/humanizer 基本相同
- 纯指令型
