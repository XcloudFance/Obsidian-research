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

