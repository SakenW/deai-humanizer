<div align="center">

# deai-humanizer（人味）

**保留原意的中英文去 AI 味编辑技能**

`Agent Skill` · 中文主体 · 26 模式五节体系 · 声音校准 · 学术诚信内建

[![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)](#版本)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/works%20with-Claude%20Code%20%7C%20Codex%20%7C%20OpenClaw-black.svg)](#安装)

</div>

---

## 它做什么

识别并去除 AI 生成文本的写作痕迹，让文字自然、有人味——**同时严格保留原意**：事实、数字、否定、条件、时间、归因和作者态度一个都不丢。「可能」不能改成「确定」，「大家觉得」不能改成「我以前觉得」。

这不是「过 AI 检测器」的工具；本技能的立场是**把写作变自然**，并内建学术诚信守则（不做检测规避、不代写）。

## 核心特性

- **26 模式五节体系**（源自上游 v3.1.0 骨架）：A 铺垫代替陈述 → B 公式化节奏 → C 拔高与借权威 → D 公式化排版 → E 聊天与草稿残留 → F 中文表达补充检查
- **六维声音校准**：提供写作样本后，先分析句长、用词、标点、口头禅再改写——改的是痕迹，不是你的声音
- **领域适配表**（8 类）：技术文档 / 商务邮件 / 创意写作 / 营销 / 学术 / 考试答案 / 观点分析 / 日常沟通
- **中文平台风格表**（5 类）：知乎 / 小红书 / 微信公众号 / 朋友圈 / 学术
- **中文专属检查**：ZH01–ZH31（层叠的「的」、四字词排比、互联网黑话、感叹号滥用……）+ 本地补充 L01–L06
- **44 → 26 模式完整映射**：旧版 44 种模式的价值全部去向可查（见 [INTEGRATION-NOTES.md](INTEGRATION-NOTES.md)）
- **检测模式**（audit-only）：只诊断不改写；Turnitin / 学业场景内建诚信守则
- **双语示例**：中英文 Before/After 整组示例

## 安装

### Skills Manager（推荐）

```bash
skills-manager-cli skills install SakenW/deai-humanizer --git --name deai-humanizer
skills-manager-cli skills deploy --agent claude_code deai-humanizer   # 分发到你的 agent
```

### Claude Code / Codex（手动）

```bash
git clone https://github.com/SakenW/deai-humanizer.git
cp -R deai-humanizer ~/.claude/skills/    # 或对应工具的 skills 目录
```

## 使用

对 agent 说：

- 「去掉这段文字的 AI 味」／「humanize this」
- 「只检测这段文字的 AI 痕迹，不要改写」（检测模式）
- 「按知乎风格改写这段介绍」（平台适配）

默认输出：改写后全文 + 主要问题 + 改动说明。详细评分表（5 维 /50 分）可按需要求。

## 文件结构

```
├── SKILL.md                  # 技能主体（中文，571 行，v2.0）
├── INTEGRATION-NOTES.md      # v1→v2 融合说明 + 44→26 模式映射表 + 优化记录
├── INTEGRATION-PLAN.md       # 历史整合计划（保留存档）
├── REFERENCES.md             # 参考来源全录
├── references/               # 11 份研究文档（44 模式全表、深度调研、来源研究）
└── tests/                    # 学术诚信边界测试用例（Turnitin 场景）
```

## 版本

**v2.0.0**（2026-11-01）：骨架升级至上游 v3.1.0（A–E 五节 25 模式 + F 中文补充 #26–31），融合本地 44 模式体系全部独有价值，新增 31 条中文检查点与语义保真规则。

路线图：v2.1 计划融入 [anti-defensive-writing](https://github.com/Kiterlin/anti-defensive-writing)（反防御性写作体系）与 [no-negative-echo](https://github.com/LB623/no-negative-echo)（交付残留检查）。

## 上游与致谢

本技能站在以下项目的肩膀上，完整来源清单见 [REFERENCES.md](REFERENCES.md)：

| 项目 | 贡献 |
|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | v3.1.0 骨架（26 模式五节体系、统一理论、Voice 规范） |
| [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) | 中文 31 检查点、语义保真规则、中文排版习惯 |
| [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) | 检测模式与三层词汇表 |
| [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) | 模式观察的公共基线 |

## 许可

[MIT](LICENSE) © 2026 Saken
