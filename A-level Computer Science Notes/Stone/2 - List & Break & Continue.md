12 - 1 2 3 4 6 12
18 - 1 2 3 6 9 18
24 - 1 2 3 4 6 8 12 24

56 - 1 x, x, x, 56




$$
j = range(1, i+1) 
$$
这里两层循环，i就是你要判断的质数的对象
j 用来列出所有的因数，所以这里是1到i+1,就比如说24, 就把1到24全部看一遍



## List - 列表
- List是一种数据类型
- 123 - integer
- “hello,world" - str
- 列表的意义：帮助我们去在一个变量里面存储多个值，比如说几千个，几万个值
- 列表第一个要素：中括号 []
- 第二个要素：多个值用逗号隔开
- a = [1,6,3,2,4]
- b = ['nihao', 'hello']
- 我们可以通过index取值的办法取出其中的某一个位置的值
- len函数：可以用来取出list里面元素的个数


![[Pasted image 20241202112824.png]]



## 如何搞清楚质数的点
- 首先搞清楚为什么一定需要一个flag？
- 为什么flag不能写外面？

```python
count = 0
for i in range(2,101):
	isPrime = True
	for j in range(2,i):
		if i % j == 0:
			isPrime = False
			break
	if isPrime == True:
		count = count + 1

print(count)
```


## Break & Continue - 只有有循环的时候可以用
- Break的意思是打破这整个循环，直接跳出，直接结束当前层的循环，后面的直接不运行了
- Continue 直接在当前的代码进入下一个循环，跳过当前循环剩下的内容
```python
for i in range(1, 10):
	if i == 3:
		continue #后面的循环内容全部不看，进入下一次循环
	print(i)
```