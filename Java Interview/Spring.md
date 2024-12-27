## Bean




## Autowired


## IoC Container




## Java Reflection
- 当Java程序启动时，类加载器(ClassLoader)会将.class文件加载到内存中
	- When java is boot, Classloader will load .class file into memory
- 加载后会在内存中生成一个Class对象，这个对象包含了该类的所有信息
	- After loading, the memory generate a class object, which contains all metadata about this class
- 每个类在JVM中都只会有一个Class对象，作为这个类的类型信息入口
	- Every class in JVM only comes with one **Class** object, as the introduction of this class type
- .forName() 
- .getClass().getName()
- Class object can gain all attribute information
- When accessing or manipulating objects, **it would automatically generate bytecode to run.**

