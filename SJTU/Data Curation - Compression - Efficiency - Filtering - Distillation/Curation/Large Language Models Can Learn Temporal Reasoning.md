[[temporal.pdf]]
![[Pasted image 20241108015848.png]]

![[Pasted image 20241108020350.png]]

## Goal
1. 提出一个新的语言模型时序推理框架TG-LLM,通过两步走策略:

- 将文本翻译成时间图作为潜在表示
- 在图上进行deliberate reasoning

2. 构建一个高质量的合成数据集TGQA:

- 完全可控
- 需要最小程度的人工监督
- 包含多样化的时序推理类型


## Graph Splitting & Anonymization
- 首先切割一个子图，构建3跳关系
- 提取节点之间发生的事件
- 然后去重重叠事件
- 然后对实体做同义词替换来做到匿名化，因为他们不想语言模型去记忆这个CoT, 而是要让他真正的去推理
	- 提高在新实体上的泛化能力
	- 但是他们没对这个做ablation study,所以是否有效有待质疑
- 
-

![[Pasted image 20241108021332.png]]


## Quality Control
- 检测是否有遗漏的event（感觉这个很重要，因为gpt最擅长漏东西）
- 主要提高cot的过滤程度，控制推理链的可信度
- 
> [!PDF|note] [[temporal.pdf#page=3&selection=146,38,149,29&color=note|temporal, p.3]]
> > . If it cannot give the correct answer, we consider the event as possibly missing in the story, which requires further manual verification. 

![[Pasted image 20241108021539.png]]
![[Pasted image 20241108022659.png]]