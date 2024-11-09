
## Laser Printer
- Drum 是由photo-sensitive 光感的材料做成的
- 负责去被laser beam 和rotating mirror 去生成的图像记录下来
- Drum可以负责等会把paper上面的对应的图像的位置的电荷带走，从而可以让纸张把打印机里面的toner（磨粉）吸附住，这样东西就印上去了
- 然后最后吸附住之后可能会掉下来，不稳定，所以需要加热(heating)的步骤负责把它加固
- ![[Pasted image 20241109102443.png]]
- 最后一步记得把drum上面的电荷移除掉并且收集多余的碳粉

## 3D printer
- Buffer (缓存)， 缓存无处不在，负责去临时的存储等会硬件需要的内容
	- 缓存是不重要的内存，因为他是从ram或者rom里面copy 一块出来的，所以哪怕buffer里面的数据被替换了，也问题不大，可以再返回ram和rom里面获取需要的数据
		- 但是代价就是，如果你再去ram和rom需要的时间更长，速度更慢
		- 所以buffer的本质就是在加速程序的运行
- **Used digital files that stores blueprints of the object to be printed**
- **Object is then built layers by layers**
- **Object is then cured / hardened by UV light (Ultra Violet)**

## Speaker & Microphone
- Analogue Data: 物理信号，声音，移动，键盘输入，鼠标移动
- Digital Data: 纯属就是binary data, computer understandable data
- DAC: Digital to Analogue Converter - 数据转物理信号的芯片
- ADC: Analogue to Digital Converter - 物理信号转数字信号芯片


- Microphone - 振动产生移动，移动通过磁场产生电流
	- consists of a diaphragm, cone, with wrapped coils on the permanent magnet
	- Sounds creates by vibration through the air
	- Diaphragm vibrates when receiving the sounds and then causes cone and coils to vibrate
	- This move forwards and backwards causes the magnetic field to be disturbed, inducing eletric currents(产生电流)
	- then the currents are hereby sampled by computer to become digital data
- Speaker 扬声器 - 二进制数据产生电流，转换成振动然后再发出来
	- 