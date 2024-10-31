[[BRIEF Bridging Retrieval and Inference for Multi-hop Reasoning via Compression]]
> [!PDF|note] [[BRIEF.pdf#page=1&selection=66,0,75,0&color=note|BRIEF, p.1]]
> > To enable learning compression for multi-hop reasoning, we curate synthetic data by extracting atomic proposition expressions that encapsulate distinct factoids from the source documents to compose synthetic summaries.

## Intuition
- 命题能以简洁且自包含的自然语言形式封装独特事实
- 可以通过链接不同命题间的信息建立逻辑连接
- 比基于token或句子级别的压缩更自然,更容易被下游模型理解和使用

## Question Composition
- 构建问题的步骤
	- single hop question X和RAG获取到的文档D
	- The sampled documents D are fed into open-source LLMs, which are prompted to compose a t-hop question ˆx and its answer ˆy.
	- 定义一个bridge entity， 用来负责交互出新的问题
		- 答案不能是bridge entities之一 
		- bridge entities不能出现在多跳问题中 
		- 要能找到完整的推理路径 
		- 每个分解的单跳问题都能被单个命题正确回答 
		- 命题必须来自不同文档
	- r