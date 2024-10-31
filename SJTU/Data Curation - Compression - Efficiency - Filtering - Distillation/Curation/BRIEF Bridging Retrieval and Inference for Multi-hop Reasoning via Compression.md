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
		- 这一步侧面说明可以让gpt4或者高性能模型去实现
		- LLaMA-3-70B-Instruct 这里使用的llama3 去做，其实目的很简单就是为了开源模型only
		- 
	- 定义一个bridge entity， 用来负责交互出新的问题
		- 答案不能是bridge entities之一 
		- bridge entities不能出现在多跳问题中 
		- 要能找到完整的推理路径 
		- 每个分解的单跳问题都能被单个命题正确回答 
		- Proposition必须来自不同文档
	- 多跳问题的答案合成摘要作为groundtruth再让t5训练，最后让t5可以天然的直接生成summary

## Proposition 是如何构成的
```python
# 原始文档
doc = """Prior to restoration work performed between 1990 and 2001, 
         the tower leaned at an angle of 5.5 degrees, but the tower 
         now leans at about 3.99 degrees. This means the top of 
         the Leaning Tower of Pisa is displaced horizontally 3.9 
         meters (12 ft 10 in) from the center."""

# 分解成命题
propositions = [
    "Prior to restoration work performed between 1990 and 2001, the Leaning Tower of Pisa leaned at an angle of 5.5 degrees.",
    "The Leaning Tower of Pisa now leans at about 3.99 degrees.",
    "The top of the Leaning Tower of Pisa is displaced horizontally 3.9 meters (12 ft 10 in) from the center."
]
```

通过加了proposition作为增强之后的likelihood和加了之前的likelihood进行比较，如果有提升则加入array,如果取提升top-k个进行组合