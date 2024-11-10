- Serial File Organization
	- 顺序存储
	- The serial file organisation method physically stores records of data in a file, one after another, **in the order they were added to the file**.
- Sequential File Organization
	- sequential的存储顺序是按照给定一个**字段(field)**进行排序的
	- serial存储的顺序是直接按照文件被插入的时间，sequential存储的顺序是按照给定的field的排序方式（id, 字符串字母序）

## Hashing Algorithm
a = {1,3,6,5}

我现在的任务是寻找5是否在数组里面，linear search一个一个拿出index一个个找去比对
O(n) -> Big O notation 衡量复杂度的一个指标
n表示数字的个数，O(n)的意思是说，这个算法的时间复杂度**最坏情况**是要循环n次
Bubble sort: 两层for循环，两两交换，直到当前这一轮结束，最外层的循环判断是否还需要交换，如果不需要交换说明数组已经是有序的，可以直接跳出冒泡排序, O(n^2)
n
n-1
n-2
n-3
n-4
1


那么哈希算法有没有办法加快寻找的速度？
35, 69, 230, 132, 55 --- 要插入的数字

index: 0,1,2,3,4,5,6,7,8,9
都是空的
取余数(modulus) remainder

算出来的余数叫hashcode, 把数字或者这个value存到指定的hashcode的对应的数组上
35 % 10 = 5
69 % 10 = 9
230 % 10 = 0
132 % 10 = 2




a[5] = [35] -> [55] -> [15] -> [5]


当我需要搜索，132是否在数字里面的时候，我也要对即将搜索的数字取一次hashcode
132 % 10 = 2
然后我得出来这个数字可能在2这个位置上，于是到数组里面搜索2这个位置上是否为132

我要找的是22
22 % 10 = 2    -- 22和132数字不一样，那就是找不到

比如说我要搜索45, 我就先取hashcode是5, 然后搜索这个linkedlist里面一个个找是否有45这个数字

**hashcode算出来是一样的会导致hash conflict** 

## Sequential Access
- Finding a particular record. Search one and the after until the file is found or the key field is exceeded / the whole file list has been searched thoroughly
- Serial File -> 物理的顺序一个个找，从头到尾找不到才结束
- Sequential File -> 按照key field的index找，如果找到的index已经超出了我要找的index,就代表已经找不到了

8999这个位置开始
9000
9001
9002

8999 + offset

## Direct Access
- Sequential File, directly calculate the location of the content by using the offset. But need to store the location of the index
- Random Organization File, a hashing algorithm is used on the key field to calculate the address of the file location where a given record is stored. 
	- 就是先取一次哈希值，计算出来存在内存的哪个位置，然后直接拿出来对比


![[Pasted image 20241110130756.png]]


- open hash就是直接存储在下一个有空的空间
- closed hash 就是直接存储在overflow的地方，接着overflow的值继续存（这种就是一般开了一个链表一个接着一个存）


## Protocol - 协议
- a set of rules between computers to communicate
- 