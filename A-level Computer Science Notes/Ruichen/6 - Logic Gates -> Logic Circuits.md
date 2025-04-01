- 这单元会学的东西：
	- 布尔代数 -> Boolean Algebra
		- 0 and A = 0
		- 1 OR A = 1
		- A or A = A
		- A and A = A
	- 特殊的逻辑电路
		- flip-flop ->  SSD nand-based circuit -> used to store 1 bit
			- SR flipflop
			- JK flipflop
		- 加法器
			- half adder - 半加器
			- full adder - 全加器
	- 布尔代数的化简
		- 表格化简
		- 手动化简


## Sum of Products
- Sum 和
- Product 积 - 乘法的结果
- SoP的意思就是好几个乘法的式子加在一起的结果
- ABC +ABC' + A'B'C
- 这个式子就是一个SOP, ABC这样的其实是A * B * C 就是一个product
- 三个products 加在一起就是sum of products
- 这是一种将所有可能的变量全部放到每一个项里面的办法，但这个式子通常都可以化简，除非你找不到任何只相差一个字母的项去互相抵消，不然就可以一直化简

- 我们要化简之前，可以先把式子由SoP的形式写出来，可以通过truth table的方式快速写出来

AB + AC

| A   | B   | C   | OUT |
| --- | --- | --- | --- |
| 0   | 0   | 0   | 0   |
| 0   |     |     |     |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |
