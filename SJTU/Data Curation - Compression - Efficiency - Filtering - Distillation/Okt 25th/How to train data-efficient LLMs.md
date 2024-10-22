## Perplexity Scoring
![[Pasted image 20241022153226.png]]
[[Data-efficient LLM.pdf]]
- perplexity scoring has a length bias or in-distribution bias, where LLM quality scoring can escape from it.
- Enlightenment: Actually [[SuperFiltering - IFD  & Perplexity]] summarizes the same pattern but didn't figure why different scales of models perform different measurement in terms of perplexity.

- Model: T5-Large (800M)  C4 Dataset - For Pretraining
- 

全篇抨击perplexity过滤方法倾向于筛除有用的例子，保留一些无厘头的内容，上下文能力不够好，判断文本单纯用max likelihood等等。

他们的方法