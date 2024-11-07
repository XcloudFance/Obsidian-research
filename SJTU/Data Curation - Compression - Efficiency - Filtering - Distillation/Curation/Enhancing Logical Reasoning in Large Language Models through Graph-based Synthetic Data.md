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
- 保证下一个要走的邻居节点的采样概率为1 / num_of_neighbors, 平均随机采样

Step 2: 数据增强

- 排列:对推理链中的三元组重新排序
- 边噪声:添加连接链外节点的边
- 边方向翻转:随机翻转部分边的方向

最后通过输入一条chain并且转换为自然语言的形式


基础模型： 
- 主要模型：Mistral-2-7B-Instruct 
- 对比模型：GPT-4
## 实验结果

基础模型：
- 主要模型：Mistral-2-7B-Instruct
- 对比模型：GPT-4

三种系统配置：
1. FS (Few-shot)：
   - 不进行微调
   - 使用5个示例进行少样本学习
   
2. SFT-S (Supervised Fine-tuning on Stories)：
   - 只在原始训练集上进行监督微调
   
3. SFT-S+k：
   - 在原始训练集和k个合成样本上微调
   - CLUTRR：k ∈ {2000, 5000, 10000}
   - StepGame：k ∈ {500, 2000, 5000}


1. 基本性能：
- SFT显著优于FS
- 合成数据进一步提升性能
- 跳数增加性能普遍下降

2. CLUTRR数据集：
- SFT-S+k持续提升性能
- 在中高复杂度(6-10跳)改进更明显
- 可以接近GPT-4性能

3. StepGame数据集：
- 合成数据带来显著提升
- 超过了GPT-4和SFT-S
- 数据量增加效果更明显

4. 提示策略：
- FS下ETA-P表现较差
- SFT下ETA-P效果显著 （本文）
- 提示工程需要配合训练

5. 通用性保持：
- 在标准基准上性能稳定
- 某些情况下略有提升
- 没有灾难性遗忘

##  数据集 StepGame: A New Benchmark for Robust Multi-Hop Spatial Reasoning in Texts

![[Pasted image 20241108013507.png]]

```json
DatasetDict({
    train: Dataset({
        features: ['story', 'question', 'label', 'k_hop'],
        num_rows: 50000
    })
    validation: Dataset({
        features: ['story', 'question', 'label', 'k_hop'],
        num_rows: 5000
    })
    test: Dataset({
        features: ['story', 'question', 'label', 'k_hop'],
        num_rows: 100000
    })
})

```
