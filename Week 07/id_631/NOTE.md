1. 位运算
	1. 十进制和二进制相互转换
	2. 位运算符操作
		1. 左移 << 数字整个左移，空出来的地方补 0，0011 => 0110
		2. 右移 >> 数字整个左移，空出来的地方补 0，0110 => 0011
		3. 按位或 | 两个二进制数字，有一位是 1，或结果就是 1，0011 1011 => 1011
		4. 按位与 & 两个二进制数字，有一位是 0，或结果就是 0，0011 1011 => 0011
		5. 按位去反 ~ 0 变成 1，1变成0 0011 => 1100
		6. 按位异或(相同为零，不同为一) ^ 两个二进制数字，同为相异就是 1，同为相同就是 0， 0011 1011 => 1000
	3. 位运算实战
		1. 判断奇偶
x %2 == 1 等价 (x & 1) == 1
x %2 == 0 等价 (x & 1) == 0
		2. 除二
x = x / 2 x = x >> 1
		3. 清零最低位的1
x = x & (x-1)
		4. 得到最低位的1
x & -x
1. 布隆过滤器和 LRU 缓存
	1. 布隆过滤器 Bloom Filter
一个很长的二进制向量和一系列随机映射函数。布隆过滤器可以用于检索一个元素是否在一个集合中，如果在表示大概率在，如果一个元素不在就一定不在
优点：空间效率和查询时间都远远超过一般算法
缺点：是有一定的误识别率和删除困难
	2. LRU Least Recently Used，最近最少使用
实现方式：HashMap + 双向链表 DoubleLinkedList
缓存替换策略：
		1. FIFO（First In First Out 先进先出）
		2. LFU（Least Frequently Used 最不经常使用）
		3. OPT（Optimal Replacement ASlgorithm 最优替换）
		4. LRU-2 [2,3] （最近两次最少使用）
		5. ARC
3. 排序算法
	1. 比较类排序
通过比较来决定元素间的相对次序，由于时间复杂度不能突破O(nlogn)，也成为非线性时间比较类排序
		1. 交换排序
		2. 冒泡排序 Bubble Sort
嵌套循环，每次查看相邻的元素如果逆序，则交换
		3. 快速排序 Quick Sort
先取标杆 pivot，将小元素放 pivot 左边，大元素放右边，然后依次对右边和右边的子数组继续快排；达到整个序列有序
时间复杂度（平均）  O(nlogn) 时间复杂度（最坏）  O(n²) 时间复杂度（最好）  O(nlogn) 空间复杂度 O(nlogn) 稳定性  不稳定
		4. 插入排序 Insertion Sort
从前到后逐步构建有序序列；对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入
		5. 简单插入排序
时间复杂度（平均）O(n²) 时间复杂度（最坏）O(n²) 时间复杂度（最好）O(n) 空间复杂度 O(1) 稳定性  稳定
		6. 希尔排序
		7. 选择排序 Selection Sort
每次找最小值，然后放到待排序数组的起始位置
		8. 简单选择排序
		9. 堆排序
		10. 归并排序 Merge Sort 分治
把长度为 n 的输入序列分成两个长度为 n/2 的子序列2. 对这两个子序列分别采用归并排序3.​​ 将两个排序好的子序列合并成一个最终的排序序列
		11. 归并排序
时间复杂度（平均）O(nlogn） 时间复杂度（最坏）O(nlogn) 时间复杂度（最好）O(nlogn) 空间复杂度  O(n) 稳定性  稳定
	2. 非比较类排序
不通过比较来决定元素间的相对次序，可以突破基于比较排序的时间下界，以线性时间运行，因此也成为线性时间非比较类排序（通常只能用于 int 数字排序）
		1. 计数排序
时间复杂度（平均）  O(n+k) 时间复杂度（最坏）  O(n+k) 时间复杂度（最好）  O(n+k) 空间复杂度  O(n+k) 稳定性 · 稳定
		2. 桶排序
时间复杂度（平均）  O(n+k) 时间复杂度（最坏）  O(n²) 时间复杂度（最好）  O(n) 空间复杂度  O(n+k) 稳定性  稳定
		3. 基数排序
时间复杂度（平均）  O(n*k) 时间复杂度（最坏）  O(n*k) 时间复杂度（最好）  O(n*k) 空间复杂度  O(n+k)稳定性  稳定