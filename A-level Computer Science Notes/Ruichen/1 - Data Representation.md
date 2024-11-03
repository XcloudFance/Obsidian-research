## Floating Point Number
- 计算机是如何存储数字的？
	- Use two's complement to store numbers
	- 正数的原码，反码(one's complement)，补码(two's complement)
	- 补码 = 反码 + 1   （负数的反码和补码需要特别转换）
	- 因为数字二进制补码被存储在计算机是有固定的大小位的，所以一般来说如果不够8位要补全8位
	- 10001 -> 0001 0001   八位存储
	- 如果考试问你为什么overflow，比如说两个数字相加的场景，
		- 1111 1111 + 0000 0010 这样肯定溢出
		- Overflow means the result number of bits exceeds the number of bits of adding numbers
	- 为什么需要补码？因为补码之间可以让计算机方便计算减法，比如说5 - 2 可以直接看成5 + (-2)

## 二进制的浮点数如何转换成十进制
![[Pasted image 20241103123447.png]]

- 先把Mantissa算出来，因为每一个位置都对应十进制的一个分数，2^-1, 2^-2,2^-3 以此类推
- mantissa的十进制这边就是45/64
- 然后把2的E次方的E也算出来，发现是4
- 2^4就是16,然后M和2^E相乘之后就得到了他原来的十进制数字
- 1011 = 11
- 0.010 = 0.25
- 你也可以先把小数点用E移动了，然后再算出各自的整数位和小数位再相加，也是ok的

## 十进制小数转二进制浮点数
11.25如何转回来二进制的浮点数？
11 -> 1011.01

Mantissa是8位，exponent是8位
1011.01

接下来normalize一下
0.101101     记载一下，exponent是4

因为mantissa一共是8位
所以在后面补1位
01011010  （mantissa）
4 转补码的步骤写出来，写出来之后是100
100 就是exponent






07
007

0.70000
0.700000000000000




小数位是从上往下看，整数的才是从下往上看
小数是* 2然后整数是/2
0.01
0.25 *  2 = 0.5      ->0
0.5 * 2 = 1.0          ->1



## 经典问题
- What happen if mantissa overflow?/ What happen if the given number stored in 8-bit mantissa?  0.1+0.2 不等于0.3
	- Mantissa is not enough to precisely store the floating number
	- Thus we need to expand more bits or borrow some bits from exponent to store it
- Whats the trade-off between mantissa and exponent?
	- Mantissa represents the **preicison of various range of numbers.**
	- Exponent represents the size of numbers.
- 8bit mantissa and **4-bit exponent**, what is the **normalized** minimum positive floating point number in this system?
	- 0100 0000   exponent能多前就多前
	- 说人话就是要让exponent直接是一个能表达的最小数字，也就是1000
	- -0.01 > -0.1  >  -0.2 
	- 1111 1111   0111
- -12.375的小数表达，用8bit mantissa和8bit exponent
- 12.375        
- 12   -> 1100
- 0.375 -> 0.011
- 1100.011
- 0.1100011
- 1.0011100 + 1 = 10011101 - 负数 -12.375的mantissa

- 11100011    向右移动4位 exponent就是100

- Why do we use normalized form?
- ![[Pasted image 20241103133002.png]]
	- 这边要注意normalized就是要清除除开符号前面的前导0,不然exponent位置会浪费，mantissa也会浪费从而导致结果的数字可能并不是最精确的
- 


## 负数二进制浮点数转十进制小数
表格法
- 10110001.11
- 0.11 = 1/2 + 1/4 = 0.75
- -128 + 32 + 16 + 1 = -79 + 0.75 = -78.25

另外一种做法
- 10110001.11 补码
- 10110001.10 反码
- 01001110.01 原码
- 1001 110 -> 2 + 4 + 8 + 64 = 78
- 0.01 -> 0.25
- 78 + 0.25 = 78.25
- 别忘了最开始这是个负数，所以是-78.25
- 



- 7.25   10bit mantissa 6bit exponent
- 7 -> 111
- 0.25 -> 0.01
- 111.01
- 0.11101 * 2^3
- 0.111010000 * 2^3
- 1.000101111 + 1 = 1.000110000
- 

	