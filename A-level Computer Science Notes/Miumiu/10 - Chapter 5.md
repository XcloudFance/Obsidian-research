signed integer - 最左边的那一位是符号位
and unsigned integer - 所有位置的数字都是二进制的表达大小的一部分

**1**100 1101  - signed integer
如果是有符号整数，这个最左边这个1就是负号，代表一定是负数
如果是无符号整数，最左边这个1也是属于二进制的一部分，把8位全部带进去算成十进制
	得出来一定是个正数 （0或者0以上的数字）



## Operating System
- Provides user interface
- provide an environment for application to be executed
- Control the hardware communication
- Process users' requests

## Driver
- 驱动的作用就是给每个peripheral 或者是input output device 提供服务
- OS 只能通过驱动去和这些CPU以外的硬件进行communicate
- 