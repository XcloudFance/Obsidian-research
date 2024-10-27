KiB

KB - 1000 - 10 ^ 3 -  **base 10** number
B**i**nary - 1024 - 2 ^ 10 - **base 2** number

1 Bit  相当于就是binary number的一位

> [!NOTE] Presentation
> 11011 - 5 bits

**1 Byte = 8 bits**
1 KiB = 1024 Bytes
1 MiB = 1024 KiB
1 GiB  = 1024 MiB

1 KB = 1000 Bytes
1 MB = 1000 KB
1 GB = 1000 MB



## Image Representation
---

###  Bitmap 位图
- Consists of **pixels**, of each represents a specific color by binary number.
	- pixel is the smallest unit in bitmap to represent a single color
	- more pixels mean **larger file size**, but **better quality**
- When zooming in, the bitmap image get **pixelated**

- Resolution 分辨率 - pixels的个数
	- 3840 * 2180 images - 长3840pixels, 宽是2180pixels
	- **Color Depth** - 色深 - How many number of bits taken by each color in pixels
		- 普通图片是由RGB组成的，每个颜色通常8个bit
		- Color Depth: 24 bits
		- Each pixels needs to take up 24 bits to store.
		- 4 bits - 2 ^ 4 = 16种可能
			- 0000, 0001, 0010, 0011, 0100, 0101, 0110, 0111, 1000, 1001, 1010,1100,1101 ,1110, 1111
		- 8 bits - 2 ^ 8 = 256种可能
	
	- File Size Calculation
		- Number of pixels * Color Depth
		- 3840 * 2180 * 3 Bytes = 
	- 
	
- Bitmap stores its **metadata** in **file header** (the beginning of the data of the file)
	- metadata: basic information about this image
		- Author
		- Color Depth
		- Pixels
		- Dates of taken
		- location
	- 

	- RGB - Red Green Blue - 255

### Vectoric 矢量图
- Made up of **drawing lists** and **drawing objects**
	- Drawing Lists are **set of commands** defining the vector
	- Drawing Objects are **mathematically** calculated shapes like circles, lines, rectangle
	- **Properties**: Properties of each object are the basic **geometric data** which determine the **shape** and **appearance**. (每个图像的属性)
	- 
- When resize the image, need to re-calculate each objects
- Advantages
	- File size is relatively smaller than normal bitmap
		- because it only stores the needed objects and commands instead of brutally storing each pixels
	- When zooming in, no quality is lost - 和bitmap相反
- Disadvantages
	- Looks unreal - Bitmaps looks like real-world images
	- Every time needs to re-calculate the relative coordinates of objects
	- 




## Two's complement
This is how a computer stores binary numbers
在计算机里面，数字的长度是固定的，8bit, 16bit或者计算机分配的指定bit,如果没说默认就8bit
0010 0101 - 这就是计算机如何存储37这个数字的
- 正数的two's complement和他的本身的二进制是一样的
	- 正数的原码，反码，补码都是一样的
- 补码诞生的意义就是为了区分负数并且支持天然的加减法
- 45 - 32 = 45 + （-32）
- 补码的最左边的1bit表示carry bit - 符号位
	- 如果carry bit = 1, negative
	- carry bit = 0, positive
- 补码最左边的数字其实也表达最大的数字的负数
- 8 bit能表达的补码的最大数字是 127, 最小的数字 -128
- 6 - 7 = -1
- 0110  + 1001 =   1111   (-1)
- 如果遇到overflow怎么办？
	- 因为相加的结果的bit number超过了原来数字相加的number of bit


27 % 2 = 13 .... 1
13 % 2 = 6 .... 1
6 % 2 = 3 .... 0
3 % 2 = 1 .... 1
1 % 2 = 0 .... 1

- -27 - 直接计算版
	- 当正数转换 - 11011
	- 补全8位 - 0001 1011  - 注意负数最左边必须是1
	- Convert into one's complement - 1110 0100
	- Convert into two's complement - 1110 0101    这个就是-27的补码
	

37 % 2 = 18 …… 1
18 % 2= 9 ...... 0
9 % 2 = 4 ...... 1
4 % 2 = 2 ...... 0
2 % 2 = 1 ...... 0
1 % 2 = 0 ...... 1

37(Denary) = 100101 (Binary)

## Encoding of Character Sets
- Each character in character sets has an unique binary representation
- 7 bit - 2^7 possibility
- ASCII - 7 bits - only include alphabets and basic marks
- Extended ASCII - 8 bits - include more european alphabets
- UNICODE - 4 bytes - Larger storage needed - but supports global languages


## Sound

Analogue data - 模拟信号 - 指的是现实生活中的物理信号，是continuous
Digital Data - 数字信号 - 其实就是0 和 1 计算机可理解的方式(computer understandable) - 是discrete

是通过Sampling 采样的方式去获取声音信号的
These samples (amplitudes) are **encoded** as a **binary number sequence**
### Sampling Rate 采样率
Number of samples taken per unit time - 表示每个单元时间（1s）取几次样

### Sampling Resolution
解析度 - 表示一个样本有多大
Number of bits per sample

## Bit Rate = Sampling Rate * Sampling Resolution
表示一秒有多大
How many bits per second

Bit Rate *  Number of seconds  = File Size
