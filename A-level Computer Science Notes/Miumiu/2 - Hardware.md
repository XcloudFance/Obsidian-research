## Memory and Storage
- Memory 内存 - 
	- It wont save the data when power off.
	- Used to store **temporary** memory of **running programs**.
	- Normally faster than Storage
	- Main Memory 主要内存 由下面两个组成：
		- **RAM**
		- **ROM**
		- 
	- Storage 存储 - 指的是你手机要**永久保存**的数据的量
		- 256GB 512GB 1024GB(1TB)
		- When the power is off, the data in storage can be still kept
		- non-volatile - 不易变的
		- 代表硬件
			- Hard Disk (HDD, SSD) - internal
			- Optical Misc - 光盘 - external
			- Flash Drive - external
		- external, 便携，可以用来备份，但是访问速度(access bandwidth)不够快
		- internal, 就是速度是被完全利用的，倾向于存储电脑系统本身和重要的不经常移动的内容
	
-


## RAM - Random Access Memory
- Volatile Memory - 断电之后程序数据不会保存
- 用来存储临时正在运行的程序的数据
- RAM通常需要更快的访问速度(access speed),通常比ROM快
	- DRAM - Dynamic RAM
		- The circuit and structure is simpler to be built
			- Only consists of **one transistor and one capacitor**
			- **Cheaper** than SRAM - less expensive to purchase
		- Has to be **refreshed to update data regularly.**
			- Thus **slower in access** speed than SRAM
			- Use **more power**
		- used to running program data or most of temporary data.
	- SRAM - Static RAM
		- used to store **buffers** - buffer的意思是缓存
		- consists of more complex circuits, thus more expensive to be built
		- Faster in access
		- **No need to be freshed regularly, thus need less power**
		- Each bit stored in **flip-flop** - 电路组成
			- flipflop是一种特殊的电路，可以用来存储1bit的数据
			- NAND 组成的或者是NOR组成的



## Buffer - 缓存
- Can be either Hardware(SRAM) or Software (video)
- Buffer普遍表示**较快的内存**，而你通常又不需要存储太大的数据的时候，就需要buffer,因为这一部分内存随时可以丢掉
- **当Buffer 被清空的时候 / 里面的数据被使用完清空后，触发系统中断(System interrupt)**
- Printer Buffer - 打印机缓存
	- Storing the file to be printed in buffer
	- So that when the printer starts working, it gets the content of data from buffer directly
	- 



## ROM  - Read-Only Memory - Main Memory
- Slower than RAM but cheaper than RAM
- SRAM > DRAM > ROM > (USB) flashdrive / removable disk > Optical Disc - speed
- Non-volatile memory: when the power is off, the data is still being kept
- **Store BIOS and some bootup instructions of operating systems**
	- BIOS是你开机的时候最先进入的地方
	- bios才是真正引导你到真正的操作系统的地方
	- bootup instructions 就是开机指令
	- the basic input/output system (BIOS）is charged in booting up operating system into RAM.
	- 
- Store **operating system kernels** 
![[Pasted image 20241102105647.png]]

### PROM, EPROM, EEPROM
- PROM - Programmable ROM
	- Only can be programmed once after it is created
	- Can only be read, cannot be modified or deleted
- EPROM - Erasable PROM
	- 意思就是可以通过UV light把数据清除了，然后再reprogram（重新写入数据）
	- 缺点：就是要把chip 拿出来之后才能清除数据
- EEPROM - Electrically EPROM
	- 正如他的名字，是使用电去存储和修改数据的
	- Can erase or modify the data without chips being removed
	- Uses electrical singals to store and erase data

## Hard Disk (HDD,SSD) - Secondary Storage
---
### HDD - Magnetic 方式 - Hard Disk Drive
- magnetic field 的方向就这个数据是0或者1
- ![[Pasted image 20241102111957.png]]
- HDD就是由sector和track组成的，数据都是存储在这个track和sector上面
- **Read-write head** for seeking data through tracks and sectors.
	- Readwrite head can read binary signals by the change of the direction of magnetic field
- Platter(盘) is placed in the middle of the hard disk on the spindle(转轴)
	- Platter rotates in a very high speed by spindle
	- sectors and tracks to store data
		- where data is encoded as magnetic patterns
- When writing, writing head is charged with current, which causes magnetic field variation in hard disk
- When reading, the variation of magnetic field in the disk produces currents to read head and then encode as binary electrical signal.
- Disadvantages 缺点:
	- Not suitable for moving scenarios, since the data might be lost due to movement.
		- Platter is speedingly rotating thus easy to get affected
	- Not reliable enough.


### SSD - Solid State Drive - Electric 方式
- electron to store binary pattern
- **NAND-based flash memory / 也可以是NOR**

- Consists of a grid(一个横纵二维的晶格) with rows & columns that has 2 transistors at each intersection:
	- Control Gate: Control the flow of electrons to write or read.
	- Floating Gate: 存储 Stores electrons to represent 1 or 0.
- 小知识点：
	- HDD之所以比SSD慢是因为HDD是需要旋转到指定的位置让读写头再读写，所以比较慢
	- SSD直接定位grid里面坐标去读写，所以很快，但是电路组成比较复杂，所以很贵
- Expensive, faster, reliable
- lighter, smaller and movable
- 





![[Pasted image 20241102113610.png]]




## Embedded System - 嵌入式系统
- 相对于现实最经常听说的operating system, embedded system没有这么多功能，只负责专注自己的部分，并且呢专门用于小的硬件设备，或者家具等等
- Only perform **specific functionality.**
- Have **dedicated hardware** with it.
- Small computer systems such as **microprocessors** **that are often a part of a larger system**

- Advantages:
	- Easy to mass produce - 方便去量产 - 因为比较简单
	- Require less power consumption
	- Rather stable because it has no moving parts
- Disadvantages:
	- Different hardware has different standards, thus only experts can fix bugs or maintain it
	- Lack of user-friendly guidances. Difficult to learn how to use
	- Difficult to update new functions or systems
	- Cannot dynamically program new functions in the system.
	- 