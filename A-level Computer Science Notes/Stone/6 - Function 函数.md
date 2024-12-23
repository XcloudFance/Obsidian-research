- 函数其实就是功能，写一个函数需要告诉编程语言这个功能在执行的时候要跑哪些代码
```python
def example():
	print("this is an example")
	print("this is line2")
	print("xxx")
	print('xdfwef')



def add(a, b):
	return a + b # return是不会输出的，只会把这个结果告诉外面的人


def hanshu():
	print("ni hao")
	hanshu()



c = add(1123123,123123123)   #这个地方add执行完后会把结果，也就是返回值 传给c
d = add(add(1,2), 3)
print(c * 20)
```


- 函数声明后要记得使用
- 调用函数的时候，函数内部的代码会被执行


## 函数里面的参数(Parameter)
- 参数的意义就是让用户使用函数的时候把值传进去
- 函数内部按道理不能访问外面的变量
- 所以当我们使用函数的时候需要告诉它我们要传入的值是什么




## 函数 - 返回值 (return value)
- 返回值的用法就是直接
	- return a + b
- return第一个作用：就是直接让函数停下来，相当于函数的终止的地方，后面的代码都不会执行
- return第二个作用：是把返回值传到外面，一般是执行的结果


## Recursion 递归
- 递归是可以使用函数自己本身的
- 大问题分解成小问题的思想，我们叫他分治(Conquer and Divide)
