## Concepts
- Class - base type that can have attributes and methods
- Instance - a variable that is initiated by a specific class
- Instantiation - Instantiate / Realize / Implement the class into an object.
	- 实例化的时候反正都是变量，是会在堆栈空间开一个指定的位置，然后变量指过去那个位置
	- 而且这个位置的大小就是一个class的大小
	- 并且attribute,method都是存放在里面的
- static function: 其实就是没有self 这个parameter的function. 可以直接不需要被实例化直接使用，但是不能使用实例里面的变量，因为就没有self
- factory function: 前面后面两条下划线，有特殊的用处，叫公厂函数， __ init __
	- constructor: 构造函数，当这个类被instantiated的时候会调用
- private attributes: 私有成员，意思是你要给这个class声明变量，但是你又不想外面的人观察或者修改里面的value, 这时候在变量名字加两条下划线就可以做到，当变成私有成员的时候只有这个类里面的method才可以被调用

- encapsulation 封装：
	- 如果你希望一个成员被调用和修改，但是希望他约束在某个规则底下
	- 做法就是把变量本身设成私有的，然后额外增加俩个函数，一个叫setter一个叫getter，专门服务于这个变量
	- 自然你可以在setter里面设定自己的if或者其他你想要额外执行的代码
	- 
- 