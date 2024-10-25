[[LAB.pdf]]


Taxonomy-based methods: 用分类并且解构数据集的方式实现了data curation
![[Pasted image 20241024215315.png]]
## Motivation
如果是普通的distillation 类的人工数据合成，缺少对数据的多样性和质量的考虑，随机采样样例去重生成只会导致输出的内容性能也无法提升

Taxonomy model让这个任务本身“平均化“了，不是针对任何特定的任务，而是雨露均沾的全部都有。不做专门focus的生成可以让teacher model去生成更多其他的东西而不是只注意在模型觉得有意思的任务上

（其实感觉和Entity的那边有股莫名的雷同）

![[Pasted image 20241025094420.png]]

random采样和taxonomy 采样的输出分布情况

