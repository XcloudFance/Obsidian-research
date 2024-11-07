[[logical reasoning.pdf]]

## Logical Graph
> [!PDF|red] [[logical reasoning.pdf#page=2&selection=19,7,46,19&color=red|logical reasoning, p.2]]
> > Let G=(V, E, R) represent a relational graph with a set of nodes V, a set of edges E between the nodes, and a set of relations R expressed in first-order logic. 


## Goal
generate synthetic examples of graphstructured data from such relation graphs to adapt LLMs for targeted reasoning tasks.

> [!NOTE] 目标
> 生成一个由关系型的图结构数据去加强LLM的逻辑推理能力

他们也一样构建了一个类似Synthetic Continued Pretraining的Entity Relation Graph, 并且同样也使用Adjacent Matrix表示entity之间的关系， 也使用probability去实现稀疏图（而不是简单的所有entity都有联系的稠密图）


不同的是，他们使用permutation去枚举所有关系


Sub-graph Sampling:

Step 1: 随机游走采样

- 输入:关系图G、游走长度l、转移概率矩阵π
- 从随机节点v0开始,进行长度为l的随机游走
- 避免重复访问节点以防止循环推理
- 收集游走路径中的边形成推理链

Step 2: 数据增强

- 排列:对推理链中的三元组重新排序
- 边噪声:添加连接链外节点的边
- 边方向翻转:随机翻转部分边的方向
