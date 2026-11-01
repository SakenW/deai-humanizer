# 参考来源全录（REFERENCES）

deai-humanizer v2.0 的每一个组成部分都来自下面这些项目与研究。按贡献类型分组，说明各来源被采纳的内容及其在 v2.0 中的落点。

---

## 一、核心上游（骨架与主体）

### 1. [blader/humanizer](https://github.com/blader/humanizer) — 英文原版上游

- **起点**：v2.5.1 —— 声音校准（voice calibration）与二次审查（2nd-pass audit）方法；9 条额外模式
- **现骨架**：v3.1.0 —— v2.0 采用其 A–E 五节 25 模式体系（含统一理论「Why AI text sounds the way it does」、Voice 规范、What to return 交付模式、每模式假阳性防护）及 F 节 #26（回复重解释）
- **落点**：SKILL.md 主干结构、26 个模式定义与英文标识
- **注意**：上游 v3.0.0 对齐 Wikipedia 后将「同义词循环」「虚假范围」移出 AI 痕迹清单，v2.0 已同步修正（旧版曾误判为 AI 痕迹）

### 2. [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) — 中文版上游

- **贡献**：基于 v3.0.0 与 PR #39 重做的中文体系 —— 31 个中文检查点（ZH01–ZH31）、语义保真规则（事实/数字/否定/条件/时间/归因/作者态度不可丢，「可能」不能改「确定」）、编辑约束与优先级、中文排版习惯、文件保护规则
- **关联来源**：其中 [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)（简洁表达与编辑检查）经由该版本引用
- **落点**：SKILL.md「编辑约束与优先级」「F. 中文表达的补充检查」章节

---

## 二、方法论来源（模式与评分体系）

### 3. [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) v3.3.0

检测模式与三层词汇表、量化硬限制（如破折号每千字 ≤1、标题无 emoji）。→ 落点：SKILL.md 检测章节与交付前检查清单；references/full-patterns.md

### 4. [OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster](https://github.com/OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster)

量化硬约束、风格审计脚本思路、「而是」禁用规则。→ 落点：SKILL.md 核心规则 #7（拒绝同义回环）与量化限制；full-patterns.md

### 5. [aaaronmiller/humanize-writing](https://github.com/aaaronmiller/humanize-writing)

12 分评分体系、节奏技法、内容类型细分。→ 落点：SKILL.md 详细输出模式的五维评分表；领域适配表

### 6. [marc-ko/ai-flavor-remover](https://github.com/marc-ko/ai-flavor-remover)

「杜绝新 AI 味」原则、展示而非说教（show, don't tell）。→ 落点：SKILL.md 声音校准与改写原则

### 7. 宝玉「菜谱」方案

写作风格 Skill + 记忆系统组合，在初稿阶段就避免 AI 味。→ 落点：SKILL.md 声音校准（先采样后改写）的使用建议

---

## 三、研究与数据来源（references/ 中的研究文档）

### 8. [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing)

模式观察的公共基线；上游 v3.x 与之对齐（部分旧模式改判为人类习惯）。→ references/source-3-wikipedia-signs-of-ai-writing.md

### 9. elatia humanizer-zh 研究

中文化改写实践研究。→ references/source-1-elatia-humanizer-zh.md

### 10. humanize-chinese 研究

中文去 AI 味技能对比研究。→ references/source-2-humanize-zh.md

### 11. ClawHub 六技能对比

平台风格适配（知乎/小红书/公众号/学术）、n-gram 检测思路。→ references/source-5-clawhub-skills.md；SKILL.md 平台风格表

### 12. Web 研究（Surfer SEO / cnblogs / 腾讯云）

困惑度（perplexity）与突发性（burstiness）理论、中文特有 AI 特征、提示词模板。→ references/source-6-web-research.md；SKILL.md「统一理解」章节

### 13. Copyleaks 实战复盘

检测器实战观察（作业模板骨架、标准答案解释句等）。→ references/full-patterns.md 模式 33–38

---

## 四、本地自建研究资产

- **references/deep-research-report.md** —— 深度调研报告（AI 味指数、可核查断言密度、同义回环、免责声明堆叠、合规路线图）
- **references/full-patterns.md** —— 44 种模式全表（中英对照，v1 体系；v2.0 经映射表融入新骨架）
- **references/exam-answer-notes.md** —— 英文考试/作业答案场景的诚信边界补充
- **tests/turnitin-integrity-cases.md** —— 学术诚信红队测试用例（4 案例）
- **INTEGRATION-PLAN.md / INTEGRATION-NOTES.md** —— 两代整合的计划与说明（含 44→26 完整映射表）

---

## 五、相关工作（计划于 v2.1 融入）

- [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) —— 反防御性写作体系（移除过早道歉、冗余免责、多层对冲，同时锚定必要范围）：与本技能的「清理免责声明堆叠」规则同源深化
- [LB623/no-negative-echo](https://github.com/LB623/no-negative-echo) —— 交付残留检查（交付文案不残留被否方案痕迹）

---

## 伦理立场

本技能定位为**把写作变自然**，不是「绕过 AI 检测」工具。对学术与考试场景：只做诊断与正当语言编辑，不承诺降低检测分数、不代写、不协助规避学术审查（见 tests/ 中的边界用例）。

## 许可

本仓库 [MIT](LICENSE)。所参考的上游项目许可以其各自仓库为准（blader/humanizer、op7418/Humanizer-zh、anti-defensive-writing、no-negative-echo 均为 MIT；Wikipedia 内容遵循 CC BY-SA）。
