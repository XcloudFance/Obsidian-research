## Output - 输出
- 在屏幕上打印一串文字
在pseudocode里面伪代码如何使用output？
什么时候需要用到output？ 就是当你需要把结果或者其中的过程展示给别人看的时候
也可以output用来输出提示词

``` VB
OUTPUT "Hello,world!"

OUTPUT "abcdefg"

OUTPUT "1234"

DECLARE code: STRING
OUTPUT "请输入你的验证码:"
INPUT code      // 这样就表示输入的验证码会放到yanzhengma这个变量里面去
```

## INPUT  - 输入
- 代码在执行到input语句的时候会等待用户输入，当用户输入完之后会把用户输入的内容加载到对应**变量(Variable)**里面


## 变量 - 可变的量 - 用来存储一个值，并且随时可以被更改
- 用一个符号，也就是变量名来代表这个值
- 在伪代码里面每一个变量他的都有自己的数据类型(Data Type)

```
DECLARE name: INTEGER

INTEGER - 整数 - -1,-2,3,4,100

STRING - 字符串 - 是由双引号把一串文字括起来的数据 "hello,world!"   "123"




```



## 书的loan 的 数据可以有哪些？
- BookID
- BorrowerID / Username
- PeriodOfTime

Identifier 的规范 - 唯一标志符
- 只要是我们取名的东西都要符合规范

DateOfBirth - DOB - 生日的日期，是不能说Birthday

valid / Invalid
nm/12 - invalid
nm+12 - invalid
nm_12 - valid

## Loop - 循环
FOR loop    - count loop 计数循环，表示知道循环的次数
WHILE loop   - conditional loop   - 把条件放在前面 
REPEAT..UNTIL loop  - conditional loop - 把条件放在后面 - **post-conditional loop**


注意伪代码的assignment操作是箭头，不是等号
```
DECLARE numbers : ARRAY[1:10] OF INTEGER

array declare的时候是需要告诉上界和下界，也就是所谓的范围，如果我写[1:10]意思就是1，2,3,4,5,6,7,8,9,10都可以存储，都有位置，且类型都是integer
numbers[1] <- 99
numbers[2] <- 456
numbers[4] <- 666
numbers[10] <- 1000


我想请问1000他存不存在于numbers里面？怎么寻找？

FOR i <- 1 TO 10
	if numbers[i] = 1000 THEN
		OUTPUT "1000是存在的"
	ELSE
		OUTPUT "1000是不存在的"
	ENDIF
NEXT i

这个代码的作用是从numbers里面找出每一个值，每一个都去问一下是否为1000,如果找到了的话马上output, 1000是存在的


```