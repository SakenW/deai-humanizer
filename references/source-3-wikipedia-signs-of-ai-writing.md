# 参考资料 3：Wikipedia - Signs of AI Writing

来源：https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing

---

## 核心原理

LLM（大型语言模型）使用统计算法来猜测接下来应该出现什么内容，基于大量训练材料。因此，其输出倾向于回归均值——即产生统计上最可能、适用于最广泛情况的通用结果。

这同时是 LLM 的优势和检测 AI 生成内容的"线索"。例如，LLM 通常在训练数据中看到名人被用积极、重要的语言描述，因此倾向于省略具体的、不寻常的、微妙的事实（这些在统计上是稀有的），用更通用的、积极的描述（统计上常见的）来替代。

这就像一张肖像画：在越来越大声地宣称画中人独特重要的同时，肖像本身正在从一张清晰的照片模糊成一幅笼统的素描。主题同时变得不那么具体和更加夸张。

## 主要检测维度

### 1. Undue Emphasis on Significance, Legacy, and Broader Trends
LLM 常常夸大主题的重要性，添加关于任意方面如何代表或贡献于更广泛主题的陈述。

### 2. Undue Emphasis on Notability, Attribution, and Media Coverage
LLM 仿佛在向读者反复强调主题的知名度，经常列出报道来源而不说明这些来源具体说了什么。

### 3. Superficial Analyses
LLM 倾向于插入对信息的表面分析，通常关于其重要性、认可度或影响。常通过在句末附加现在分词短语来实现。

### 4. Promotional and Advertisement-like Language
LLM 即使被要求使用百科全书式语调，输出也常偏向广告式或旅游指南式写作。

### 5. Vague Attributions and Overgeneralization of Opinions
LLM 用模糊的第三方观点来支撑论述，如"专家认为"、"观察者指出"。

### 6. Other Common Patterns
- 过度使用加粗和格式标记
- 破折号滥用
- 公式化段落结构
- 不自然的引用风格
- 三段式列举偏好

## 关键提醒

- 不要仅依赖 AI 内容检测工具（如 GPTZero），它们有不可忽视的错误率
- 不要过度依赖自己的判断——研究表明即使是有经验的 LLM 用户，正确率也只有约 90%
- 这些模式是描述性的，不是规范性的；它们是观察结果，不是规则
- 许多 AI 写作元素也可以在社论、博客或同人小说中找到
