# 参考资料 2：Humanize-zh

来源：https://clawhub.ai/bbintom123321-lab/humanize-zh

---

## 安全评估摘要

- ✓ Purpose & Capability: 名称和描述（humanize Chinese AI text）与 SKILL.md 内容一致
- ℹ Instruction Scope: 运行时指令纯粹是风格改写指南
- ✓ Install Mechanism: 纯指令型，无代码文件
- ✓ Credentials: 不需要环境变量或凭证
- Persistence & Privilege: always is false，用户触发

## 注意事项

该技能鼓励添加个人轶事和主观语言（如"我之前也遇到过类似情况..."），在使用时需注意：

1. 在非敏感文本上测试以确认风格变化符合需求
2. 可能导致编造的个人经历或无法验证的说法——审查输出的事实准确性
3. 避免在法律、医疗等高风险内容上使用
4. 注意 agent 可能自主调用该技能——初始阶段监控输出
