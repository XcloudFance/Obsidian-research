-100 convert to two's complement
100 / 2 = 50 …… 0
50 / 2 = 25 …… 0
25 / 2 = 12 …… 1
12 / 2 =6 …… 0
6 / 2 = 3 …… 0
3 / 2 = 1 …… 1
1 / 2 = 0 …… 1

0110 0100 -> 8 bits -> 100的情况
1001 1011 -> one's complement -> - 100
1001 1100 -> two's complement -> -100

## 什么是Communication?
- 传输之间讲的语言，其实就是一套属于自己的规则和做法风格，这个就叫protocol
	- 不同的protocol自然是无法相互交流的，因为标准都不一样，无法做到decoding


- 什么是internet
	- 生活中提到的网络，只要和互联网有连接的，和外面有连接的所有东西所有app所有传输都是internet
	- QQ Wechat Instagram - 属于internet 但是不属于world wide web万维网
	- 
- 什么是world wide web - 万维网
	- 特指网页和网页的资源的网络，如果是遵循文件传输，邮箱传输，app传输这种特别的规则就不属于www
	- 
## IP Address - IP地址
- The location of the internet. **Used to identify different devices or invidiuals on the internet.**
- Unique
- 可以用来建立互联网之间彼此的传输
- 注意：一个network用一个ip address

- WAN - 广域网
	- Geographically large or covering bigger area
	- Takes time to transmit data - More congested than LAN
	- Usually share the **bandwidth** with other users on the internet
		- bandwidth其实就是你的网速，the number of bits to be transferred within a unit time
		- bandwidth higher means more bits to be transfered in one second
		- bandwidth lower means less bit transferred and causes more time to wait for the transmission
- LAN - 局域网
	- home, school, shopping mall
	- geographically smaller area to be covered
	- less congested since not many users in the network
	- 
- public IP address: is used in WAN (Wide Area Network)
- private IP address: is used in LAN (Local Area Network)

- IP 地址的example：180.152.227.166   这是我的公网ipv4地址
	- ipv4 每一个数字最多只能到255 - Each number cannot exceed 255
	- 而且由四个数字，用小数点隔开组成 - Consists of four numbers split by dots
	- 1111 1111 -> 这是255的二进制，八位
	- **ipv4的真正定义是一个由四个八位的二进制数字组成的地址，一共是32-bit**
		- 32-bit address
		- 2^4  0000 0001 0010 0011 .....
		- 2 ^ 32种可能
- Why dont people use IPV4?
	- Maximum 2 ^32 different IP address available, which is not enough for the need of global internet users
	- We can adopt IPV6 as the IP address, which contains more bits to store
	- **Less secure to transfer data because it has no encryption(加密).**
- IPV6地址：
	- Consists of 8  16-bit numbers. Hence it is a **128-bit address**
	- Able to store a large number of users
	- More secure becuz the transmission protocol has its own encryption
	- 缺点：
		- ipv6地址not compatable with ipv4 所以很难全部迁移
		- ipv6 address is too difficult to be remembered
- **1050:0000:0000:0000:0005:0600:300c:326b** - ipv6 的例子
	- 可以缩写：挑中间0最多地方直接省略，其他的不能省
	- 105::5:0600:300c:326b
	- 两个引号表示中间的0都被我省略了


## Client-Server Model   客户端服务器模型
- Client 指的是 客户， 一般来说都是普通的用户
- Server指的是服务器，负责提供指定服务给所有的Client
	- File Server - 文件服务器
		- File Sharing among different users
		- Allow to share a link that contains files
		- Can download or upload files from servers or to servers
	 - Streaming Server - 流服务器
		 - 专门用来live streaming(直播)， 传输视频信号
	- Printer Server -  打印机服务器
	- Database Server - 数据库服务器

## Peer-to-peer 模型
- All devices acts independently to store data
- Every peer can become servers or clients to share data over the network
- Decentralized Network - meaning there is no central server in the network


## Subnetting 子网
- Subnetting mask - 子网掩码
- Subnetting: Split the whole network / IP address network into smaller sub-networks
- IP地址里面其实是会规范哪些bit是用来表示networking,**哪些bit是用来表示host ID**
- IP地址networking意思是说会告诉你这是哪个网络，相同网络的ip地址是会共享这一部分的地址
	- 192.168.0.1 - 32bit 二进制
	- 192.168.0.2
	- 192.168.0.3
- 这三个ip地址都是属于同一个网络底下出来的，因为他们前缀的networking ID是一样的
- 一般情况下来说是由“子网掩码”去定义哪一部分是“不变的“， 以及哪一部分是属于”会变的“
- 一般来说前面的是network,后面的是host, host一般都是用来identify different devices in the same network
- 11100001. 10101111. 0000000.00000001 - 32bit IPV4地址
- 111111111.
