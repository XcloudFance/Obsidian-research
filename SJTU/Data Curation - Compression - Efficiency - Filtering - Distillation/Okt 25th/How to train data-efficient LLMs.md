## Perplexity Scoring
![[Pasted image 20241022153226.png]]
[[Data-efficient LLM.pdf]]
- perplexity scoring has a length bias or in-distribution bias, where LLM quality scoring can escape from it.
- Enlightenment: Actually [[SuperFiltering - IFD  & Perplexity]] summarizes the same pattern but didn't figure why different scales of models perform different measurement in terms of perplexity.

- Model: T5-Large (800M)  C4 Dataset - For Pretraining
- 

全篇抨击perplexity过滤方法倾向于筛除有用的例子，保留一些无厘头的内容，上下文能力不够好，判断文本单纯用max likelihood等等。
并且提出了两个方法：Ask-LLM和Density Sampling

Density Sampling - 比起计算X到Y的相似度，要花费N2的时间，直接用一个LSH 最近哈希桶去平滑这个搜索会更好，降低到N log N



![[Pasted image 20241022213034.png]]

他们觉得，ask-llm 不仅提供了质量的权衡的时候考虑到了逻辑，perplexity只是看到了“difficulty", 然后density sampler 提供了在潜在语义的coverage