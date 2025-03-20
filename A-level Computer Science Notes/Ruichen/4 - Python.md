- 
## Paper 4 - Practice
- 基础语法
	- 输入/输出
	- if 条件语句
	- 循环语句：for, while
	- 基础数据结构
		- list
		- tuple
		- dict
	- 进阶的数据结构
		- tree
		- hashtable
		- stack
		- queue
		- linked list
	- 排序算法
		- 冒泡排序
		- 插入排序
		- 快速排序
	- 搜索算法
		- linear search
		- binary search
	- OOP - Object Oriented Programming - 面向对象的编程
		- 关于如何定义一个class， class本身其实就是python的类型
		- Inheritation
		- Polymorphism
		- Encapsulation
		- Abstraction

8小时 - 12个小时用于paper4
剩下的时间全部做paper3

## Paper 3
- Number Representation 
- Networking
- Hardware
- 编译原理 - Compiler Principle
	- 会教你如何去构建一个编程语言的逻辑
	- 词法器(Tokenizer) 和 语法器
	- Finite status machine (FSM) - 可以用来表达程序的状态
	- 类似于正则表达式的语法
- Security
	- 对称加密
	- 非对称加密
	- 加密的协议 - SSL TLS怎么加密的
	- 数字签名 - Digitial Signature
- Operating System (System Software) - 操作系统理论


- 整理theory的复习材料给你
- 让AI出一点python实践的习题给你

## Python语法
- 输出
```python
print("hello,world!")
print("hello,C++!")
```
print函数默认结尾都会换行，是因为有一个默认参数，叫end
end每次都会被默认赋值为\n
所以如果你不想换行，可以把end修改了

```python
print("hello,world!", end = '')   # 表示把end修改成空字符，意思就是结尾什么都不输出
print("hello,C++!")
```

可能你需要将多个print连成一行的时候会用到修改end的时候

### 输入函数
input()

input函数会在命令行窗口**等待**用户的输入，回车表示结束
输入的结果会放成返回值返回

input里面也是可以填一**个字符串**的，这个字符串每次在你要求用户输入的时候会先输出，作为**提示词**
考试的时候如果让你写：prompt user to input xxx
你就记得在input函数里面写一些提示，User friendly 


## Variable & Data Type

- Identifier 标识符， 变量的名字，函数的名字等等
	- 要保证identifier的命名的规范，比如说正确的大小写，不能有特殊的字符
- 一个变量的组成：
	- 变量名(Identifier)
	- 变量的初始值(Initial Value)
	- 的类型 - python是弱类型语言，所以不是强制的
- int
- bool    - 由True和False组成，注意t和f都是大写
- str - 字符串
- 