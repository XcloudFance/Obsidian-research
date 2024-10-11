## Noise Impacts towards RAG

- From [https://mp.weixin.qq.com/s/KPRNclbD3UB46Ck_se-xgw](https://mp.weixin.qq.com/s/KPRNclbD3UB46Ck_se-xgw)
- 《The Power of Noise Redefining Retrieval for RAG Systems》

![[image 5.png]]

- Introducing **noises** (unrelated documents) can **improve** performance
- **Including related documents but no answer** in it **decreases** the performance
- 从相关文档的位置应靠近查询，否则模型很难关注到它。
- 与查询语义相关但不包含答案文档对RAG系统极为有害，后续研究应该想办法从检索到的文档中剔除这些干扰项。