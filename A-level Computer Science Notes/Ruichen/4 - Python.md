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
- float - 小数
- bool    - 由True和False组成，注意t和f都是大写
- str - 字符串
- **list - 列表 - 由中括号括起来的collection type - 有复数个元素**
- **tuple - 元组**
- **dict - dictionary 字典**

## Selection Statement - 分支语句 / 选择语句
- 本质上就是在说代码可以分开成不同条件执行不同的语句，就叫Selection Statement
- 其实就是if语句
- if语句就是判断括号内的条件是否成立，如果成立就执行A,不成立就执行else的B
```python

if condition:
	print("hello,world!")
	print("只要是属于if语句的都必须是同一个缩进")

```


```C#

if (a == 1){
	console.writeln("hello,world!");
}
```


## Loop
- for循环， 里面是需要学一个函数，叫range函数

```python

for i in <这里填一个可以迭代的对象>:
	你要循环的代码
	
```
可以迭代的对象一般就意味着复合元素的变量
比如说list, tuple, dict这种都是复合元素，都可以放在in的后面
str其实也是复合元素
str其实可以看成是好几个单个字符的组成，所以for i in str变量也是可以成立的


为了不手打1000个元素来实现1000次循环，我们要使用range函数，可以帮助我们快速生成数列
比如说1,2,3,4,5,6,7,8,9,10可以写成: range(1,11), 注意这里写11是因为range的数列长这样:
1 <= number < 11
取上不取下


range(2,98) 其实是2到97

for循环一般是你知道要循环几次的时候，哪怕这次数本身是一个变量，你也可以使用for循环
while循环，是你不知道大概要循环几次，但只要满足条件就要一直反复执行的语句



如果我写的是5 ** 2
意思就是5的2次方

如果要写开方呢? 5 ** 0.5
