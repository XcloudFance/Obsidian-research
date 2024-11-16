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
	- 
	- 
	- 
- LAN - 局域网
	- home, school, shopping mall
	- geographically smaller area to be covered
	- less congested since not many users in the network
	- 
- public IP address: is used in WAN (Wide Area Network)
- private IP address: is used in LAN (Local Area Network)

- IP 地址的example：180.152.227.166   这是我的公网ipv4地址
	- ipv4 每一个数字最多只能到255
	- 而且由四个数字，用小数点隔开组成 - 