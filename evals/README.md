# 行为评估（evals）

验收技能行为的固定测试：给定输入文本，跑技能，按 graders 验收输出。不测检测分数，只测行为是否符合契约。

## 运行方式

手动流程：把 `*/prompt.md` 里的任务文本交给加载了本技能的 agent，对照对应 `graders.md` 逐条验收。
自动化（规划）：接入行为评估 runner（参照 sepia 的 evals workflow 结构），graders 由判定模型或人工逐条打分。

## 测试清单

| 测试 | 场景 | 核心验收点 |
|---|---|---|
| deaify-wechat-article | 公众号文章去味 | 事实零丢失 / venue 契合 / 反指纹白名单执行（不过度执法） |
| deaify-release-note-cn | 中文发布说明去味 | 数字与 breaking change 全保留 / 价值宣言清除 / 条目化 |

## 基线

技能版本 2026.11.06.2 首次建档。sepia（SEPIA-2026）的 evals 结构为本文件的格式参照；测试文本与 graders 均为本仓库自写。
