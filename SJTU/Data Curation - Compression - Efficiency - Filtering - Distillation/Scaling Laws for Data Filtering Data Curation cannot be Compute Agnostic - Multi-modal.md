## Scaling Laws for Data Filtering: Data Curation cannot be Compute Agnostic - Multi-modal

- Data Filtering must be compute-aware / cannot be compute-agnostic
- Related Work
    - 2021 - 有直接对clip相关度计算低于28%直接过滤的行为，这样的操作和LLM计算损失过滤法并无多大区别
    - 还有对图中文字ocr后mask掉提升generalization的 (T-MARS)
- Empirical Results
    
    - 过滤后数据在大量计算后不会取得更好的结果，其实和前面的噪声提升性能差不多的道理，这里也提醒了data flitering不适合大量多次训练来暴力提升性能
    - 而且由于过滤后数据变少了很多（大约10%残留），多次训练让模型重新看了好几次相同的数据，这也是一个过拟合的思路
    
    ![[image 6.png]]
    
- 因此直觉地去寻找一个trade-off

![[image 7.png]]

- **结论：取20% - 30%的数据最为合适**