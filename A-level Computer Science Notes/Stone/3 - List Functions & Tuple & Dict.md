## Append函数 - 追加
- 这些函数都是在已有的list变量上面执行的
- append函数会在list的尾部，**就是最后一个地方插入一个新的值**
- 这个值是你自己给的
- list1.append(5)


## Insert 函数 - 插入
- 第一个值表示位置，就是插入的位置
- 第二个值表示你要插入的值是多少
- ![[Pasted image 20241203150739.png]]
## Sort函数 - 排序函数
- 这个函数不需要传入任何参数
- 他的意思是把列表里面的元素按照顺序排列
- 直接 list.sort()就可以了
- 会直接对列表里面的元素排序

## Slice 切片  - 这个不是函数
- 日常使用列表可以用index拿出一个位置的值
- 如果我需要连续的拿出从第a位到第b位的值，要怎么做？
- 切片会直接拿出来一整个list
- ![[Pasted image 20241203152011.png]]
## 如何让list里面的东西倒着出来


![[Pasted image 20241203153154.png]]



## Dictionary 字典 - Dict
- 这是一个特殊的列表，里面的结构是key-value
- 现在的key不同于list的index, 可以放字符串
- Person = {"Name":"Ken",  "Age":18 , "Gender": "Male", "Hobby":"Piano}
- print(Person['Gender'])
- print(Person['Hobby'])

![[Pasted image 20241203154223.png]]![[Pasted image 20241203154246.png]]


## For循环到底in后面跟的东西是什么
- 可迭代的对象 - Iterative Object
- 表示这个对象这个变量里面的值是有很多个的情况
- for i in range(a,b)
- range函数就是帮助你快速生成一个可迭代的对象，从a到b
- list也是一个可迭代的对象
- **for i in num**的这个i本质上是从列表里面复制粘贴一个出来
- ![[Pasted image 20241203155138.png]]