![[Pasted image 20241207195100.png]]

## Public IP  VS Private IP
- Public IP 是指在WAN (Wide Area Network)里面的IP地址
- Private IP  是指在LAN (Local Area Network)里面的IP地址
- Public IP is provided by **ISP**(互联网提供商), private IP is allocated by **routers**
- Using NAT(Network Address translation) to translate public ip to private ip and vice versa.
- 

## Static IP VS Dynamic IP
- Static IP never changes
- It is used when the machine wants to be remembered by some websites
- Higher upload and download speed

- Dynamic IP changes at every regular time period
- It is more secure since hard to be tracked after a certain period.
- Maintenance cost is lesser - 维护的成本更便宜
	- Reduce the waste of IP address - 减少了IP地址的浪费， because those unused IP can be re-assigned to other machines
	- 




## DNS Server - Domain Name Server
- 负责把domain name 转换成对应的IP地址并且返回给客户
	- Responsible for converting domain name into corresponding IP address and returned to clients
- 


## URL

Example:
https://www.bilibili.com/video/BV194zXYkEyv/?vd_source=d656a6cc2800e6edefdadc447df9109e

https: 指的是网页传输的协议(Protocol)， 意思就是网页用了什么标准传输
www.bilibili.com - Domain name 域名， 相当于服务器的别名，这样有助于去记忆，而不是直接去记服务器的ip地址，更复杂

## What happened when user is using a browser?
- The user keys in the URL into browser
- The browser requests DNS server to get the corresponding IP address
- DNS received, and look up IP address **level by level**
	- DNS服务器自己有三层，如果找不到会继续往上找，直到完全找不到为止
	- 如果找不到会直接return一个error
	- 
- After the client really get the server's IP address, it starts to build up the connection.
- Server will send the **HTML** code and other resources back to the browser
- Browser renders the website **by interpreting the HTML code.**

