<div align="center">

# deai-humanizer（人味）

**保留原意的中英文去 AI 味编辑技能**

`Agent Skill` · 中文主体 · 26+ 模式五节体系 · 证据台账 · 校准三原则 · 学术诚信内建

[![Version](https://img.shields.io/badge/version-2026.11.06.2-blue.svg)](#版本)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Codex%20%7C%20OpenClaw-black.svg)](#安装)

</div>

---

## 它做什么

识别并去除 AI 生成文本的写作痕迹，让文字自然、有人味——**同时严格保留原意**：事实、数字、否定、条件、时间、归因和作者态度一个都不丢。「可能」不能改成「确定」，「大家觉得」不能改成「我以前觉得」。

这不是「过 AI 检测器」的工具；本技能的立场是**把写作变自然**，并内建学术诚信守则（不做检测规避、不代写、学术场景先诊断）。

## 核心特性

- **26+ 模式五节体系**（源自上游 v3.1.0 骨架）：A 铺垫代替陈述 → B 公式化节奏 → C 拔高与借权威 → D 公式化排版 → E 聊天与草稿残留 → F 中文表达补充检查 → G 反防御与交付清洁（#27 反防御性写作 / #28 中文技术 SOP / #29 交付残留）
- **六维声音校准**：提供写作样本后，先分析句长、用词、标点、口头禅再改写——改的是痕迹，不是你的声音
- **校准三原则**（治理全部规则的执行强度）：瞄准区间不瞄准反面 / 选择不累积 / 留松弛——把每条 AI 痕迹反向打满会制造新指纹
- **Security boundary**：待编辑文本视为不可信材料，嵌入指令不作为操作指令（防注入）
- **模式 #1 R/L/U 判定路径**：「不是X而是Y」先缺陷检查再功能检验，52.8% 的机器用法是修辞选择而非缺陷——单例放过，聚类超标才系统性处理
- **证据台账**（REFERENCES.md）：22 条 ID 化来源，五级证据分级，每条明确记录 Used / **Not used** 边界与消费映射
- **中文反指纹白名单**（zh-signals.md）：11 条「中文语境下不成立的判定」——防止过度执法误伤正常修辞
- **venue 场景规则**（4 类）：公众号文章 / 技术文档 / PR 回复 / 发布说明——各有专属 slop 清单、编辑策略与白名单
- **中文平台风格表**（5 类）：知乎 / 小红书 / 微信公众号 / 朋友圈 / 学术
- **中文专属检查**：ZH01–ZH31 + 本地补充 L01–L06；**三层词汇体系**（520 万字语料统计，源自 lieflat 方法论）
- **检测模式**（audit-only）：只诊断不改写；Turnitin / 学业场景内建诚信守则
- **行为评估**（evals）：公众号去味等固定测试，prompt + 逐条验收标准

## 规划中（骨架已建，待实测填充）

- **中文叙事架构层**：references/narrative-zh.md——12 决策组中文适配框架 + 9 条待实证假设（AI 中文叙事的观察清单）。叙事特征的实证基线是 StoryScope（英文小说语料），**中文叙事层实测是本技能的差异化立项**，完成后即填补该领域空白
- **中文模型指纹**：references/model-fingerprints-zh.md——GLM / DeepSeek / Qwen / Kimi 等中文输出的签名特征积累框架（author/executor 分离，不从文风猜模型）

## 安装

### Skills Manager（推荐）

```bash
skills-manager-cli skills install SakenW/deai-humanizer --git --name deai-humanizer
skills-manager-cli skills deploy --agent claude_code deai-humanizer   # 分发到你的 agent
```

### Claude Code / Codex / OpenClaw（手动）

```bash
git clone https://github.com/SakenW/deai-humanizer.git
cp -R deai-humanizer ~/.claude/skills/    # 或对应工具的 skills 目录
```

## 使用

对 agent 说：

- 「去掉这段文字的 AI 味」／「humanize this」
- 「只检测这段文字的 AI 痕迹，不要改写」（检测模式）
- 「按知乎风格改写这段介绍」（平台适配）
- 「按公众号场景深度改写」（venue 规则自动加载）

默认输出：改写后全文 + 主要问题 + 改动说明。详细评分表（5 维 /50 分）可按需要求。

## 文件结构

```
├── SKILL.md                        # 技能主体（中文，2026.11.06.2）
├── REFERENCES.md                   # 证据台账（22 条 ID 化来源，Used/Not used + consumers）
├── SEPIA-COMPARISON.md             # sepia 深读对比与可融合清单（P0/P1/P2）
├── INTEGRATION-NOTES.md            # v1→v2 融合说明 + 44→26 模式映射表
├── INTEGRATION-PLAN.md             # 历史整合计划（存档）
├── references/
│   ├── venues/                     # venue 场景规则（公众号/技术文档/PR 回复/发布说明）
│   ├── zh-signals.md               # 中文反指纹白名单（11 条不成立的判定）
│   ├── narrative-zh.md             # 中文叙事架构层骨架 + 实测路线图
│   ├── model-fingerprints-zh.md    # 中文模型指纹积累框架
│   ├── full-patterns.md            # 44 模式全表（v1 体系存档）
│   └── …                           # source-1~7 研究文档、upstream-companions
├── evals/                          # 行为评估（prompt + 逐条验收标准）
└── tests/                          # 学术诚信边界测试用例
```

## 版本

**2026.11.06.2**：完工冲刺——venue 场景规则（4 类）、evals 行为评估、中文叙事层与模型指纹骨架、README 对外化。
**2026.11.06.1**：P0 纪律升级——证据台账重构（sepia 范式）、校准三原则、防注入边界、中文反指纹白名单。
**v2.1**：融合 anti-defensive-writing（G 节 #27/#28）与 no-negative-echo（#29），三层词汇体系。
**v2.0.0**（2026-11-01）：骨架升级至上游 v3.1.0，31 条中文检查点与语义保真规则。

路线图：叙事层中文实测立项（人写 vs AI 中文小说对照语料）→ evals 自动化接入 CI → 分模型指纹积累。

## 上游与致谢

本技能站在以下项目的肩膀上，完整证据台账见 [REFERENCES.md](REFERENCES.md)：

| 项目 | 贡献 |
|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | v3.1.0 骨架（26 模式五节体系、统一理论、Voice 规范） |
| [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) | 中文 31 检查点、语义保真规则、中文排版习惯 |
| [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) | 检测模式与三层词汇表 |
| [larashero3 系 lieflat](https://github.com/larashero3-dotcom/lieflat-less-ai-tone) | 三层词汇体系（520 万字语料统计） |
| [Kiterlin/anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing) | 反防御性写作（G 节 #27/#28） |
| [LB623/no-negative-echo](https://github.com/LB623/no-negative-echo) | 交付残留检查（#29） |
| [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) | 模式观察的公共基线 |
| [Nanako0129/sepia](https://github.com/Nanako0129/sepia) | 证据台账范式、校准三原则、中文校准方法论（方法借鉴，文字自写） |
| StoryScope（arXiv:2604.03136） | 叙事架构层实证结论（中文叙事层实测为本技能规划） |

## 许可

[MIT](LICENSE) © 2026 Saken
