这个方法的去重(deduplication)过程可以概括为以下几个关键步骤：
[[deduplication.pdf]]

Motivation:
- 社交媒体数据由于其嘈杂的特性，存在严重的冗余问题。
- 这种冗余不仅增加了模型训练的时间和资源消耗，还可能导致模型偏差。 (这里原文对语言模型判断 negative neural positive做了一个解释，说如果类似文本重复过多可能会被误解为是neutral)

![[Pasted image 20241022014131.png]]

- 传统的去重方法（如shingles和simhash）主要依赖于表面语言特征，无法有效处理语义层面的重复。
- 基于语义相似度的方法（如成对比较）计算复杂度高，难以应用于大规模数据集。


1. 训练阶段：

   a) 首先，使用KeyBERT为每个社交媒体文本提取关键词。
   b) 然后，训练一个生成模型（如T5）来预测这些关键词。训练只进行一个epoch，并应用时间维高斯噪声(TGN)来增加难度。
   c) 这个短暂的训练使模型能够学习预测常见（重复）文本的关键词，但对于独特的文本则难以准确预测。

2. 推理（去重）阶段：
   a) 使用训练好的模型为所有文本生成关键词。
   b) 比较生成的关键词与原始提取的关键词（目标关键词）。
   c) 如果生成的关键词与目标关键词匹配，则认为该文本是重复的。
   d) 移除被识别为重复的文本。

3. 去重的关键思想：

   - 重复或高度相似的文本在仅仅一个epoch的训练后更容易被准确预测关键词。
   - 独特的（非重复的）文本由于训练不足，难以准确预测关键词。
   - 这种差异使得模型能够区分重复和非重复文本。

4. 效率考虑：

   - 这种方法的复杂度为O(n)，其中n是文本数量。
   - 避免了传统去重方法中常见的成对比较，大大提高了效率。




这篇论文使用了多个数据集来评估其生成式去重方法的效果。主要数据集和效果如下：

1. 去重实验数据集：
   - MRPC (Microsoft Research Paraphrase Corpus)
   效果：
   - T5-base 生成式去重在F1等价(F1eq)上达到56.3，比基线方法shingles提高了23.4%。
   - T5-small 版本也比shingles提高了19.8%的F1eq，同时减少了6.3秒的去重时间。

2. 社交媒体语言理解任务数据集：
   主要使用TweetEval基准测试集，包含7个任务：
   - Emoji Prediction
   - Hate Speech Detection
   - Offensive Language Identification
   - Sentiment Analysis
   - Stance Detection
   - Irony Detection
   - Humor Detection (来自SemEval-2021 task 7)

效果：
- 在大多数任务中，使用生成式去重后的数据训练的模型性能优于使用原始数据或其他去重方法处理后的数据。
- 例如，对于使用LLaMA模型的情感分析任务，生成式去重减少了50.9%的训练集大小和42.9%的训练时间，同时将宏观召回率从73.0提高到73.5。

3. 通用短文本分类数据集：
   为了证明方法的普适性，还在以下数据集上进行了测试：
   - AGNews
   - Subj
   - SST-2

效果：
- 在这些通用数据集上，生成式去重也能减少训练数据大小，同时保持或略微提高模型性能。

总体来说，这种生成式去重方法在多个数据集和任务上都展现出了良好的效果：
1. 有效减少了训练数据的规模（通常在20%-50%之间）
2. 显著减少了训练时间（在某些情况下减少了40%以上）
3. 在大多数任务中，使用去重后的数据训练的模型性能与使用全量数据相当或更好
4. 在某些任务中，还能带来明显的性能提升