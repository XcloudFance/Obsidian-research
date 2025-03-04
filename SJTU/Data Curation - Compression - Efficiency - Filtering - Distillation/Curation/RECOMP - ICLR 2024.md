
[[8767_RECOMP_Improving_Retrieva.pdf]]

> [!PDF|yellow] [[8767_RECOMP_Improving_Retrieva.pdf#page=1&selection=56,48,65,78&color=yellow|8767_RECOMP_Improving_Retrieva, p.1]]
> > an extractive compressor which selects useful sentences from retrieved documents and an abstractive compressor which generates summaries by synthesizing information from multiple documents.

- 两个压缩器
	- extractive compressor
	- abstractive compressor
	- 

## Porblem Setting

> [!PDF|255, 208, 0] [[8767_RECOMP_Improving_Retrieva.pdf#page=2&annotation=950R|8767_RECOMP_Improving_Retrieva, p.2]]
> > ECOMP  compresses retrieved documents  D  with respect to  x  into a summary s  which captures core information in  D  relevant to  x  with significantly fewer tokens than  D.
- 本质上还是RAG 压缩，从相关文档内获取内容
- 

## Compressor
### Extractive Compressor
- 摘取的压缩器是通过将文档的句子拆出来，和输入的问题做相关比较，相关度最高的全部作为压缩后的summary
	- 有个potential的问题，如果作为普通数据集筛选，这样也会过拟合
	- 对于RAG感觉如果是属于multihop的关系可能capture不到
- 用的是Unsupervised Dense Information Retrieval with Contrastive Learning， 训练的数据集是在wikipedia和ccnet,也有自己的多模态版本，用MoCo的方式训练
 > [!PDF|important] [[8767_RECOMP_Improving_Retrieva.pdf#page=4&selection=91,1,102,20&color=important|8767_RECOMP_Improving_Retrieva, p.4]]
> > For the language modeling task, we generate training data using the training split of the Wikitext-103 dataset, selecting the top 20 sentences from the top 5 BM25 retrieved documents for each input context x. For the QA tasks, we generate training data using the training split and consider the top 20 sentences from the top 5 contriever-ms-marco 5 retrieved documents.
> > 


## Abstractive Compression

 Symbolic knowledge distillation: from general language models to commonsense models. I







这是一个很好的想法!让我分析一下这两篇论文可能的结合点:

1. 目标互补：
- RECOMP关注检索增强LLM的效率问题,通过压缩文档减少token数量
- CoH关注从人类反馈中学习,提升模型对齐质量 
- 结合后可以既提高检索效率,又保证输出质量对齐人类偏好

2. 具体结合方案:

A. 压缩器训练改进:
- 原RECOMP只用正面例子训练压缩器
- 可以采用CoH方法,用正负反馈序列训练:
```
"这是个不好的压缩:{低质量压缩} 
这是个好的压缩:{高质量压缩}"
```
- 让压缩器学会区分好坏压缩的特征

B. 检索-压缩-反馈的端到端框架:
1. 检索相关文档
2. 用改进的压缩器生成摘要
3. 收集人类反馈
4. 用CoH方法训练模型,同时优化:
   - 压缩质量
   - 最终输出质量
   
C. 交互式改进:
- 用户可以对压缩和最终输出都提供反馈
- 系统通过CoH学习改进双重目标:
  - 更高效的文档压缩
  - 更符合人类偏好的输出

3. 潜在优势:

- 效率提升:
  - 保持RECOMP的高压缩率
  - 通过CoH确保压缩不损失关键信息
  
- 质量保证:
  - CoH帮助系统学习什么是好的压缩
  - 最终输出更好地对齐人类偏好

- 灵活性增强:
  - 支持多样化的反馈形式
  - 可以根据具体任务调整优化目标

4. 实现考虑:

A. 训练流程:
1. 首先用RECOMP方法预训练压缩器
2. 收集压缩结果的人类反馈
3. 用CoH方法微调:
   - 压缩器
   - 主语言模型

B. 评估指标:
- 压缩率
- Rouge分数
- 人类评价
- 最终任务性能

C. 挑战:
- 如何平衡压缩率和质量
- 如何设计有效的反馈模板
- 如何高效收集人类反馈

5. 未来方向:

- 探索更多反馈形式
- 研究压缩和对齐的权衡
- 扩展到更多应用场景
- 设计更好的评估方法

总的来说,结合这两种方法有很大潜力,可以既解决效率问题,又提升输出质量。关键是要巧妙设计训练方案,平衡各种目标。这个研究方向值得进一步探索。



