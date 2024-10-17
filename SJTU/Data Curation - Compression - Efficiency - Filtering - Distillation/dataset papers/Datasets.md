### Survey
[[Xiong 等 - 2023 - Effective Long-Context Scaling of Foundation Model.pdf]]

## Long Tasks
- [[QuALITY - Question Answering with Long Input Texts, Yes!]]
- 0-shot NarrativeQA
- Qasper 2-shot
- QMSum 1-shot
> [!PDF|yellow] [[Xiong 等 - 2023 - Effective Long-Context Scaling of Foundation Model.pdf#page=4&selection=238,50,240,36&color=yellow|Xiong 等 - 2023 - Effective Long-Context Scaling of Foundation Model, p.4]]
> > The number of shots are decided based on the average sample length of each dataset (i.e., samples in Qasper and QuALITY are often much shorter than those of NarrativeQA). 

- ZeroSCROLLS   - instruction tuning evaluation
	- Summarization
	- QA
	- Aggregation


| 数据集名称       | 任务类型   | 评估指标                             | 评估方法       | Shot数  | 上下文长度  | 领域/主题         | 其他特征       |
| ----------- | ------ | -------------------------------- | ---------- | ------ | ------ | ------------- | ---------- |
| NarrativeQA | 长文本问答  | F1分数（答案与参考答案的词重叠）                | 自动评估       | 0-shot | 16,384 | 叙事文学          | 基于长篇故事的问答  |
| Qasper      | 长文本问答  | F1分数（答案与参考答案的词重叠）                | 自动评估       | 2-shot | 16,384 | 科研论文          | 基于研究论文的问答  |
| QuALITY     | 长文本问答  | EM (Exact Match，完全匹配率)           | 自动评估       | 2-shot | 16,384 | 多领域           | 复杂长文本理解    |
| QMSum       | 长文本摘要  | ROUGE-geo（ROUGE-1、2、L的几何平均）      | 自动评估       | 1-shot | 16,384 | 商业会议          | 查询式多领域摘要   |
| ZeroSCROLLS | 多任务长文本 | 多个指标：ROUGE（摘要）、F1/EM（问答）、准确率（分类） | 自动评估       | 0-shot | 未指明    | 多领域           | 10个子任务     |
| L-Eval      | 长文本评估  | 多个指标：准确率、F1、ROUGE（因任务而异）         | 未指明        | 未指明    | 未指明    | 多领域           | 6个新的长文本任务  |
| MMLU        | 多任务评估  | 准确率（正确答案的比例）                     | 自动评估       | 5-shot | 未指明    | 人文、STEM、社会科学等 | 多领域知识评估    |
| HumanEval   | 代码生成   | Pass@1（第一次生成就通过测试的比例）            | 自动执行测试     | 0-shot | 未指明    | 编程            | 函数完成任务     |
| GSM8K       | 数学推理   | 准确率（正确解答的比例）                     | 自动评估       | 8-shot | 未指明    | 数学            | 小学数学应用题    |
| TruthfulQA  | 事实性评估  | 真实性（不含虚假信息）和信息量（回答完整性）的综合得分      | GPT-3模型评估  | 6-shot | 未指明    | 多领域           | 817个问题     |
| ToxiGen     | 毒性评估   | 毒性生成率（被分类为有毒的生成文本比例）             | RoBERTa分类器 | 未指明    | 未指明    | 社会议题          | 13个少数群体    |
| BOLD        | 偏见评估   | 情感得分（-1到1，0为中性，评估偏见程度）           | VADER情感分析  | 未指明    | 未指明    | 社会人口统计        | 5个领域43个子群体 |