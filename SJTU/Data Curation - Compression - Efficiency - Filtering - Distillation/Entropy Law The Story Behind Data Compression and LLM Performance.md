h ## Entropy Law: The Story Behind Data Compression and LLM Performance

- 这篇很有意思，借用了信息论和压缩的思想去做信息压缩，真正的compression思路
- Working Steps
    - 选择压缩比最低的多个候选样本构建样本池，找到信息密度比较高的
        - 这里的intuition是压缩的比例少说明信息就多，且冗余度高的数据不具备全局多样性
    - 然后粗粒度局部选择，再选出一点数据到样本池，计算总样本池的压缩比，选择总压缩比较小的样本进来， 这一步计算了多样本之间的组合效果
    - 从样本池选一个局部样本，和其他样本逐个计算压缩比，压缩比低的话差异就比较大可以保留，为的就是O n^2的时间复杂度找全局差异最大的池子
- 其实感觉similarity之类的CLIP或词向量可以做到类似的效果，简单来说就是拉出数据多样性+压缩高效，O n^2的压缩计算比较并不是很高效，不过或许可以从信息压缩算法寻找灵感
- 还有用训练模型loss找最有价值的减少迭代次数，**这里其实甚至可以用Saliency去做，寻找有用的文本去做组合**