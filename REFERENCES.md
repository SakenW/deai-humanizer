# 参考来源台账（REFERENCES）

deai-humanizer 的每个组成部分都来自下面的项目与研究。本文件是**证据台账（evidence ledger）**：每条来源有稳定 ID、证据分级、采纳与明确不采纳的边界（Used / Not used），以及消费这条来源的规则文件（Consumers）。规则文件引用来源一律走 ID。

> 台账格式参照 sepia（Nanako0129/sepia）的 sources.md 方法论，2026-11-06 重构。变更历史见 git。

## 台账约定

- **ID**：`作者/项目-年份` 或 `项目名`，规则文件中以 ID 引用来源，不重复展开。
- **class 分级**：
  - `UPSTREAM`——上游技能，骨架或章节直接来源
  - `HEURISTIC`——编辑经验与方法论来源（未做受控实测）
  - `STUDY`——已发表研究或论文（含预印本；注明语料与局限）
  - `CORPUS`——公共语料或基线文档
  - `LOCAL`——本地自建资产（内部报告、历史版本、测试用例）
- **Used / Not used**：Not used 不是否定来源，而是明确记录「这条来源里我们有意不采纳的内容及原因」，防止未来误读回归。
- **Consumers**：消费这条来源的本仓库文件。

## 台账总表

| ID | 来源 | class | Used（要点） | Not used（明确不采纳） | Consumers |
|---|---|---|---|---|---|
| BLADER-HUMANIZER | [blader/humanizer](https://github.com/blader/humanizer) v2.5.1→v3.1.0 | UPSTREAM | A–E 五节 25 模式体系、统一理论、Voice 规范、交付模式、#26、每模式假阳性防护；v3.0 对齐 Wikipedia 后「同义词循环」「虚假范围」移出 AI 痕迹清单（已同步修正） | 上游英文 ban list 不逐字迁移（中文信号见 ZH-SIGNALS） | SKILL.md 主干 |
| OP7418-HUMANIZER-ZH | [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh)（v3.0.0 + PR #39） | UPSTREAM | ZH01–ZH31 中文检查点、语义保真规则、编辑约束与优先级、中文排版、文件保护 | 其引用的量化门槛不独立采纳（见 CONORBRONSDON 行） | SKILL.md 编辑约束、中文检查点表 |
| STOP-SLOP | [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) | HEURISTIC | 简洁表达与编辑检查思路 | — | 经 OP7418-HUMANIZER-ZH 间接引用 |
| CONORBRONSDON-V3 | [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) v3.3.0 | HEURISTIC | 检测模式清单、三层词汇表、量化硬限制（破折号每千字 ≤1 等） | 其准确率类声明不采纳（无受控实验支撑） | SKILL.md 三层词汇体系、交付前检查；references/full-patterns.md |
| OUBIGFA-BOOSTER | [OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster](https://github.com/OUBIGFA/De-AI-Prompt-Enhancer-Writer-Booster) | HEURISTIC | 量化硬约束、风格审计思路、拒绝同义回环（#7） | **「而是」全面禁用规则不采纳**——被 PENG-NOTX-2026 决策树替代（见 ZH-SIGNALS） | SKILL.md #7、量化限制；references/full-patterns.md |
| AAARONMILLER-HW | [aaaronmiller/humanize-writing](https://github.com/aaaronmiller/humanize-writing) | HEURISTIC | 12 分评分体系→五维评分表、节奏技法、内容类型细分 | 其评分不作为质量事实或检测证据（SKILL.md 输出格式已声明） | SKILL.md 五维评分表、领域适配表 |
| MARC-KO-AIFR | [marc-ko/ai-flavor-remover](https://github.com/marc-ko/ai-flavor-remover) | HEURISTIC | 「杜绝新 AI 味」原则、show don't tell | — | SKILL.md 声音校准与改写原则 |
| BAOYU-RECIPE | 宝玉「菜谱」方案 | HEURISTIC | 初稿阶段避免 AI 味的组合思路（风格 Skill + 记忆） | 记忆系统部分未实现 | SKILL.md 声音校准使用建议 |
| WIKIPEDIA-AI-WRITING | [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) | CORPUS | 模式观察公共基线；上游 v3.x 对齐后部分旧模式改判为人类习惯（已同步） | CC BY-SA：内容遵循其许可，不直接复制表述 | references/source-3-*.md |
| ELATIA-HUMANIZER-ZH | elatia humanizer-zh 研究 | HEURISTIC | 中文化改写实践观察 | 未核验的准确率与手法不采纳 | references/source-1-*.md |
| HUMANIZE-ZH-STUDY | humanize-chinese 对比研究 | HEURISTIC | 中文去 AI 味技能对比 | — | references/source-2-*.md |
| CLAWHUB-SIX | ClawHub 六技能对比 | HEURISTIC | 平台风格适配（知乎/小红书/公众号/学术）、n-gram 检测思路 | n-gram 量化不作为判定门槛 | references/source-5-*.md；SKILL.md 平台风格表 |
| WEB-RESEARCH-PPB | Surfer SEO / cnblogs / 腾讯云 | HEURISTIC | 困惑度/突发性理论介绍、中文特征观察、提示词模板 | **困惑度/突发性变化不作为保真或来源证据**（SKILL.md 交付前复核已声明） | references/source-6-*.md；SKILL.md 统一理解 |
| COPYLEAKS-POSTMORTEM | Copyleaks 实战复盘 | HEURISTIC | 作业模板骨架、标准答案解释句等工程观察（模式 33–38） | 检测器机制描述按「历史经验」对待，不作已验证机制 | references/full-patterns.md |
| KITERLIN-ANTIDEF | [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) | UPSTREAM | 反防御性写作体系→SKILL.md G 节（#27、#28），全文存档 references/upstream-companions/ | — | SKILL.md G 节 |
| LB623-NNE | [LB623/no-negative-echo](https://github.com/LB623/no-negative-echo) | UPSTREAM | 交付残留检查→SKILL.md G 节（#29），全文存档 references/upstream-companions/；技能本体已独立收编（Skills Manager） | — | SKILL.md G 节 |
| LIEFLAT-LAT | [larashero3 系 lieflat-less-ai-tone](https://github.com/larashero3-dotcom/lieflat-less-ai-tone) | UPSTREAM | 三层词汇体系（Tier 1/2/3）、520 万字语料统计方法 | 量化数字作编辑参考，不作检测证据；联动分工见 SKILL.md「技能联动」 | SKILL.md 三层词汇体系、技能联动 |
| SEPIA-2026 | [Nanako0129/sepia](https://github.com/Nanako0129/sepia) v0.13.0（⭐3641，MIT） | UPSTREAM | 证据台账范式（本文件格式）、校准三原则、防注入边界范式、中文校准方法论（三源对照：公开语料+人类侧+机器侧+规范标准）、「不是X而是Y」功能分布研究引用 | **繁体台湾 venue 数据**（MOE 规范、台湾新闻语料）——简体大陆向不适用；「不过检测器」定位（本技能保留学术正当编辑场景）；voices 人设机制；叙事层英文规则（见 STORYSCOPE-2026 行 Not used） | REFERENCES.md 本台账；SKILL.md 校准三原则、Security boundary；references/zh-signals.md；SEPIA-COMPARISON.md |
| STORYSCOPE-2026 | StoryScope（arXiv:2604.03136，6.1 万篇小说，30 特征叙事分类 93.2% F1） | STUDY | 叙事架构层实证结论与 30 特征框架——作为 fiction 路由的能力规划参考（SEPIA-COMPARISON.md P2） | **数值与处方不直接用于简体中文**：语料为英文（Books3 系），本技能未做中文叙事层实测；叙事层规则暂不进入 SKILL.md（P2 候选，立项时需中文自建语料） | SEPIA-COMPARISON.md（P2 规划） |
| PENG-NOTX-2026 | 「不是X而是Y」功能标注研究（sepia zh.md 引用：307 条机器用例，substantive 45.9% / optional 52.8% / defective 1.3%） | STUDY | ZH01/#1 的假阳性防护方法论参照：先缺陷检查（真相冲突/误归属/语用缺陷），再三功能检验 R/L/U——一刀切禁用属于过度执法 | **具体百分比不作为本技能的判定门槛**（本技能不设数值门槛的原则不变） | SKILL.md #1/ZH01 假阳性防护的理解依据；references/zh-signals.md |
| SOURATI-2026 | LLM 打磨与文本种群离散度研究（sepia 引用：重写使 1000 篇人写文本复杂度离散度收缩 21–50%） | STUDY | 校准三原则之「留松弛」的实证依据 | 英文 Reddit 语料的数值不作中文门槛 | SKILL.md 校准三原则 |

## 本地自建资产（LOCAL）

| 资产 | 说明 |
|---|---|
| references/deep-research-report.md | 深度调研报告（AI 味指数、可核查断言密度、同义回环、免责声明堆叠、合规路线图）；其公式、示例评分、政策和工具描述不作当前验证结果 |
| references/full-patterns.md | 44 种模式全表（中英对照，v1 体系；v2.0 经映射表融入新骨架） |
| references/exam-answer-notes.md | 英文考试/作业答案场景的诚信边界补充 |
| references/zh-signals.md | 中文反指纹白名单（2026-11-06 新建，参照 SEPIA-2026 zh.md 方法论，简体大陆向） |
| references/venues/ | venue 场景规则 4 件（公众号文章 / 技术文档 / PR 回复 / 发布说明，2026-11-06 新建） |
| references/narrative-zh.md | 中文叙事架构层骨架 + 实测路线图（v0 骨架，数值待中文实测，P2 立项） |
| references/model-fingerprints-zh.md | 中文模型指纹积累框架（v0 骨架，GLM/DeepSeek/Qwen 等待积累） |
| evals/ | 行为评估（README + deaify-wechat-article：prompt + 逐条验收标准，2026-11-06 新建） |
| tests/turnitin-integrity-cases.md | 学术诚信红队测试用例（4 案例） |
| INTEGRATION-PLAN.md / INTEGRATION-NOTES.md | 两代整合的计划与说明（含 44→26 完整映射表） |
| SEPIA-COMPARISON.md | sepia 深读对比与可融合清单（2026-11-06，P0/P1/P2 融合依据） |

## 分组详注（历史结构保留，条目已升级入台账）

### 一、核心上游（骨架与主体）

**BLADER-HUMANIZER**：起点 v2.5.1（声音校准与二次审查方法、9 条额外模式）；现骨架 v3.1.0（A–E 五节 25 模式体系、统一理论「Why AI text sounds the way it does」、Voice 规范、交付模式、每模式假阳性防护）及 F 节 #26。上游 v3.0.0 对齐 Wikipedia 后将「同义词循环」「虚假范围」移出 AI 痕迹清单，本技能已同步修正（旧版曾误判为 AI 痕迹）。

**OP7418-HUMANIZER-ZH**：基于 v3.0.0 与 PR #39 重做的中文体系——31 个中文检查点（ZH01–ZH31）、语义保真规则（事实/数字/否定/条件/时间/归因/作者态度不可丢，「可能」不能改「确定」）、编辑约束与优先级、中文排版习惯、文件保护规则。STOP-SLOP（hardikpandya/stop-slop）经由该版本引用。

### 二、方法论来源（模式与评分体系）

**CONORBRONSDON-V3**：检测模式与三层词汇表、量化硬限制。**OUBIGFA-BOOSTER**：量化硬约束、风格审计脚本思路（其「而是」禁用规则已被 PENG-NOTX-2026 决策树替代，见台账 Not used）。**AAARONMILLER-HW**：12 分评分体系、节奏技法、内容类型细分。**MARC-KO-AIFR**：「杜绝新 AI 味」、show don't tell。**BAOYU-RECIPE**：写作风格 Skill + 记忆系统组合（记忆部分未实现）。

### 三、研究与数据来源

**WIKIPEDIA-AI-WRITING**：模式观察公共基线。**ELATIA-HUMANIZER-ZH / HUMANIZE-ZH-STUDY**：中文化实践与技能对比。**CLAWHUB-SIX**：平台风格适配与 n-gram 思路。**WEB-RESEARCH-PPB**：困惑度/突发性理论与中文特征观察。**COPYLEAKS-POSTMORTEM**：检测器实战观察（作业模板骨架、标准答案解释句）。

### 四、本地自建研究资产

见上表 LOCAL 段。

### 五、相关工作（v2.1 已融入）

**KITERLIN-ANTIDEF**（反防御性写作 → G 节 #27/#28）、**LB623-NNE**（交付残留 → G 节 #29）均已融入，全文存档于 references/upstream-companions/。

### 六、v2.1 之后新增（2026-11-06 台账重构时引入）

**LIEFLAT-LAT**（三层词汇体系来源，Skills Manager 中央库有收录）、**SEPIA-2026**（方法论对标）、**STORYSCOPE-2026 / PENG-NOTX-2026 / SOURATI-2026**（研究依据，经 SEPIA-2026 引入，引用前已核对原文描述）。

## 伦理立场

本技能定位为**把写作变自然**，不是「绕过 AI 检测」工具。对学术与考试场景：只做诊断与正当语言编辑，不承诺降低检测分数、不代写、不协助规避学术审查（见 tests/ 中的边界用例）。

## 许可

本仓库 [MIT](LICENSE)。所参考的上游项目许可以其各自仓库为准（blader/humanizer、op7418/Humanizer-zh、anti-defensive-writing、no-negative-echo 均为 MIT；Wikipedia 内容遵循 CC BY-SA；sepia 为 MIT——本台账借鉴其格式与方法论，文字自写）。
