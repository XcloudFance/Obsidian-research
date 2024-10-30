[[Learning to Filter Context for Retrieval-Augmented Generation.pdf]]
> [!PDF|note] [[Learning to Filter Context for Retrieval-Augmented Generation.pdf#page=2&selection=79,1,95,24&color=note|Learning to Filter Context for Retrieval-Augmented Generation, p.2]]
> > (i) STRINC: whether passages contain the generation output
> >  
> >  (ii) LEXICAL overlap: how much unigram overlap the content and output has
> >   (iii) Conditional cross-mutual information (CXMI): how much more likely the generator is to generate the output when the content is provided.


![[Pasted image 20241030144747.png]]

- Strinc单纯使用字符串搜索去查看拿出来的文档是否包含文本词， 但是挑选出来的不一定包含答案，所以需要其他步骤
- Lexical Overlap可以去用于计算示例e和候选文本片段里面的句子t之间的unigram(单词)重叠程度，如果超过阈值就为1如果没有就为0
- CXMI 通过衡量互信息前后差距， 加了文档被筛选的句子和没加文档的ratio去看互信息最高的部分，但是花更多的时间![[Pasted image 20241030145317.png]]

## Context Filtering Model 额外训练
> [!PDF|red] [[Learning to Filter Context for Retrieval-Augmented Generation.pdf#page=3&selection=547,17,575,8&color=red|Learning to Filter Context for Retrieval-Augmented Generation, p.3]]
> >  To create training data for Mctx, for each training example with query q, we concatenate the retrieved passages P and query q as input, then, we apply the filter method f to obtain filtered context tsilver as output



### 测试的数据集
- ![[Pasted image 20241030145414.png]]
## 结论
![[Pasted image 20241030145505.png]]
**比用full passage好，比只使用部分passage好很多，但是和silver不相上下**
**由此可见模型学会过滤的方式明显也是不错的选择，比起传统的办法，而且语言模型复杂度时间上来说也可以比前三种叠加方法少**
