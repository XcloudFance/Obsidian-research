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
- **Spread the pressure of the server into all nodes in the peer-to-peer model**

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
- 111111111.  111111111. 111111111. 00000000   - 子网掩码 subnetting mask
	- 说白了就规定了这个网络到底有多大，意思就是有多少种ip地址可能性
	- 
- 一般来说为1的都是网络段，为0的都是host ID段
- 如果为0就表示这一部分可以随便赋予，想要多少就给多少，想到哪个数字就给哪个数字，只要在0的个数的范围内就可以
- 如果是上面的子网掩码，0有13个，意味着有一共多少ip地址？
	- 0000 0000
	- 0000 0001
	- 0000 0010
	- ……
	- 2^8种可能，

假设今天电脑室有2^9台电脑，用这个子网掩码的ip地址段的大小可以表示所有的电脑吗： 111111111.  111111111. 111111111. 00000000 





## Internet Medium
要考虑的问题
- 价格
- bandwidth
- 距离
- 抗干扰能力
- Portability - 有线网和无线网的区别
- Stability - 有线网和无线网的区别
- 有线网可以使用full bandwidth
	- 无线网如果受到干扰会导致bandwidth下降，所以会用不了full bandwidth
	- duplex双工的传输
	- wifi is half-duplex while wired network is full-duplex
	- 
- 

- Wired Network
	- Copper Cable
		- cheaper
		- cannot do the long distance
		- need enough power to transmit data
		- 
	- Fibre-optic Cable
		- more expensive for buying **dedicated** hardwares
		- can transmit long distance
		- Greater bandwidth
		- Improved Security: **difficult to be listened by the third-party**
- Wireless Network
	- Radiowave
	- Microwave
	- Satellite


## 家里的设备是如何连接到互联网的？
- 手机电脑平板都拥有一个硬件：**Wireless** Network Interface Card (WNIC) - 无线网卡
	- 作用就是可以连接wifi信号，并且和wifi进行传输上网
- 和家里的Router发出来的Radio Wave也就是Wifi进行连接
- 连接过程：Router会负责给我们的Local Area Network的设备进行allocate private IP address
- 连接后就可以通过router转发所有的互联网信息到彼此的设备和WAN之间建立连接
	- Star Topology - 星型拓扑结构
- Router会记住每个设备的**MAC地址和IP地址之间的联系**，然后负责识别和传输
- Router NAT: Router translates private IP addresses to public IP addresses AND vice versa.


## Internet Supporting Hardware

### PSTN - Public Switch Telephone Network
- Channel between two endpoints using circuit switching
	- 意思就是两边进行传输的过程的通道是专线传输
- Using telephone lines to transmit
- Lines active even during **power outage**  
- Bi-directional communication 
- Limited Bandwidth



### Bridge 和 Repeater的区别
- Bridge叫无线网放大器
	- 他本身就作为一个信号的转发器，放在信号弱和信号强的地方的中间，把wifi信号接受之后再以一个新的wifi信号传输出去给自己远处的手机和设备
	- Connect two LANs that share the same protocol, which can be **two segments of the same network**
	- **Stores all connected devices between two networks**
- Repeater叫有线的线材**信号放大器**
	- 信号放大器负责把衰减的有线信号放大一遍再传出去
	- 所以这样就可以让两条cable连接在一起组成更长的线
	- Connect two cables
	- regenerates the sent data over the network **before the signal weakens**
* Bridge用于连接两个不同的网络，而Repeater用于扩展同一个网络的范围。
* Bridge可以过滤网络流量，而Repeater只是简单地转发所有信号。
* Bridge需要配置IP地址，而Repeater不需要。






# Subneting 子网掩码
- 把一个大的网络ip分成很多个小网络，**每一个网络都由子网掩码来规定自己到底ip地址能用的范围是多少**
- IPV4的特点： 四个八位的二进制数字组成 - 一共32 bits
	- 前八位或者16位一般都是Network ID - 作用是知道自己属于哪一个网络底下的，相同网络的subnet的network ID是一样的
	- 后八位或者16位一般都是Host ID - 用来区分同一个网络下不同的设备的ID, 就是在这里保证设备彼此之间ip地址是不同的
- logic gates:
	- AND
	- OR
- 1 AND 1 = 1
- 1 AND 0 = 0
- 0 AND 1 = 0
- 0 AND 0 = 0
- OR的特点是只要有一边是1,就是1, 如果两边都是0那就答案是0

- 192.168.0.1的二进制
	- 192 的二进制是 11000000
	* 168 的二进制是 10101000
	* 0 的二进制是 00000000
	* 1 的二进制是 **11001001**
- Subnet: 255.255.255.0 的二进制  - 24


一个ip地址可以这么写：
**192.168.2**.8 :: 24 - 上面这三个不在同一个netID底下
**192.168.3**.5  ::24
**192.168.4**.7 ::24

**这个24和16就叫subnet ID**

**192.168**.2.8 :: 16 - 下面这三个在同一个netID底下
**192.168**.3.5  ::16
**192.168**.4.7 ::16

- Subnet OR the IP address
- 11111111.11111111.11111111.00000000   OR    11000000
- 11111111.11111111.11111111.  - masking 负责把我不想看到的部分mask掉
- 这样就说明了前三位被掩盖住了，说明前三个8位二进制都是我的network ID
- 后面剩下的一个8位二进制就是我的hostID

- 子网掩码只要规定了哪里是1,就代表哪里会被masked掉，就代表了那一部分专门用来表示network的区域，剩下的部分全部留给host,也就是在同一个网络底下的不同设备各取所需
- 



