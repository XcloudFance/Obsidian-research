## MoDS: Model-oriented Data Selection for Instruction Tuning

- 要考虑的数据要素
    - Diversity - Coverage
    - Quality - Non-repeated
    - Necessity
- Highlight:
    - The model finetuned with **4,000** instruction pairs selected by our approach could perform **better** than the model fine-tuned with the full original dataset which includes **214k** instruction data.
- **Quality Evaluation**
    - Reward-model-deberta v3 large-v2 model For data scoring with the abilities of **QA model evaluation, reward scoring,** and **detecting potential toxic response via ranking**
        
        ![[image 8.png]]
        
- **Diverse Data Selection (Diversity) for Seed Instructions**
    
    - The objective of the **K-Center problem** is to choose **a subset of K centers** from a given set of data points in a manner that **minimizes the maximum distance** between **any data point and its nearest center.**
        - 有点聚类的意思
    - Metrics for evaluating: **Sentence-bert**
    
      
    
      
    
    - **Augmented Data Selection**
    
    ![[image 9.png]]
    
      
    
    - 简单来说觉得自己instruction还是不够，把上面两种方法结合做出来的seed instruction丢给llm finetune又生成了一堆感觉能用的instruction做数据增强
    
    ![[image 10.png]]