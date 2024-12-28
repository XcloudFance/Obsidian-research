
Each pixel is arranged / stored in the file sequentially.
每个像素在文件里面都是按顺序一个接着一个存储的

## RLE - Run-length Encoding

RLE是一种无损压缩，压缩的算法已经写在名字里面了
run + length

aaaaaaabbbbbbc   <- 压缩前
a7b6c1                     <- 压缩后
要怎么解压？
aaaaaaabbbbbbc 把abc的次数放回来就是解压了

abcdefg <- 压缩前
a1b1c1d1e1f1g1   <- 压缩后




- lossless compression
	- 压缩后的文件是可以恢复成压缩前的样子
	- The file can be restored in the way before it gets compressed
- A -> A-  -> A
- 什么时候用无损压缩？
	- 文档类的
	- 重要信息类的

- lossy compression
	- 音频，图像，视频这种multimedia 的用有损压缩
	- 有损压缩对图像的修改是永久的，不可恢复不可逆转
	- 因为这种多媒体类的文件哪怕损耗一点质量(quality)也可以运行或者完整的被理解




## Vector Graphic
- A vector graphic c**onsists of drawing objects**
- Drawing Objects: **mathematically defined constructs**, such as triangle, line, circle
- **Drawing Lists**: A set of commands that identify drawing objects, 相当于是用命令的方式存储了可以用哪些drawing object
- Smaller file size
- Can scale up / zoom in without losing quality



## Servers
- File Server - 这个也是公司可以用到的
- Mail Server - 邮件服务器
	- 邮件服务器就是用来存储收发的邮件，学校是肯定会用到的
	- 公司也有可能用到
- Printer Server - 打印机服务器
- Proxy Server - 代理服务器
-


RAM access speed is faster while ROM is slower
RAM is volatile and ROM is non-volatile, **which means ROM can preserve the data even the power is off**

Register - the smallest unit of memory
最小的内存单元

data of **instruction** fetched from memory

**contiugous repeated colors turned into the number of reptition and the color itself**
**For example: the first line of pixel: R2 P3 G1**


## Logical Shift
- logical shift 意思是如果左移或者右移出现的空位由0来补上
	- 左移就是右边多一个0
	- 右移就是左边多一个0

## Arithmetic Shift
 - for signed integers multiplication and division
 - signed integers - 是有符号的，有负数的情况的
 - unsigned integers - 没有符号，意味着所有位置都用来存储数字，都是正数，最小的数字是0

## Cyclic Shift
- 循环移位
- 意思是左移被挤掉的会被放到右边
- 右移被挤掉的会被放到左边


## Bit Masking - 位掩码
- 位掩码 本质就是盖住某一串位置，只看指定的位置是否为0或者为1
- 1100   这是个4bit的二进制
	- 最左边那一位表示房间的灯是开的还是关的
	- 最右边的第一位表示厨房的灯是开的还是关的
- 计算机里面经常拿一个二进制的数字来表示很多种状态
- 8bit就可以表示8个不同地方的状态
- 4bit表示4个不同地方的状态
- 1100 如果我是计算机，**我只想判断最左边的那一位是否为1还是0要怎么办？**
	- 我可以选择把右边三位不需要的位置全部掩码盖掉(mask掉)
	- AND 按位取与
	- 1111(31) AND 1000(8) = 1000(8)
	- 1101 AND 1000 = 1000
	- 1000 AND 1000 = 1000
	- 1110 AND 1000 = 1000
	- **0110 AND 1000 = 0000**
	- 0101  
	- 


- 
	- if number AND 1000 = 1000 THEN
		- 房间的灯是开的
	- if number AND 1000 = 0000 THEN
		- 房间的灯是关的
	- 
	- 任何数 and 0 都是0
	- 1000就是我的掩码，用and方法把右边三位全部掩盖成0,就无论右边三位怎么变换，and后一定是0, 最后的答案只有两种情况：0000和1000， **取决于我要被掩码的数字的最左边那一位**