### 1.  数组中重复的数字
***
**在一个长度为n的数组里的所有数字都在0到n-1的范围内**。 数组中某些数字是重复的，但不知道有几个数字是重复的。也不知道每个数字重复几次。**请找出数组中任意一个重复的数字**。 例如，如果输入长度为7的数组{2,3,1,0,2,5,3}，那么对应的输出是第一个重复的数字

### `Approach 1`
排序后扫描

**Complexity Analysis**

-   Time Complexity: $O(nlogn)$
-   Space Complexity:  $O(n)$

### `Approach 2`
哈希表

**Complexity Analysis**

-   Time Complexity: $O(n)$
-   Space Complexity:  $O(n)$

### `Approach 3`
扫描数组，当扫描到下标为$i$的数字$A_i$时，设$A_i=m$，如果$A_i=i$则扫描下一个；如果$A_i \ne i$，判断$A_i$是否与$A_m$相等。如果$A_i=A_m$，那么$A_i$就是要找的数；如果$A_i \ne A_m$则1交换$A_i$与$A_m$，继续扫描下一个

**Complexity Analysis**

-   Time Complexity: $O(n)$
-   Space Complexity:  $O(1)$
### 2.  二维数组中的查找
***
在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。
### `Approach 1`
暴力搜索

**Complexity Analysis**

-   Time Complexity: $O(n^2)$
### `Approach 2`
对每一行分别进行二分查找

**Complexity Analysis**

-   Time Complexity: $O(nlogn)$

### `Approach 3`
从数组右上角出发，若$A_{ij}=Target$，则查找结束；如果$A_{ij} < Target$，剔除数组中$A_{ij}$所在的行；如果$A_{ij} > Target$，剔除数组中$A_{ij}$所在的列；不断上诉过程以缩小查找范围

**Complexity Analysis**

-   Time Complexity: $O(n)$
### 3.  替换空格
***
请实现一个函数，将一个字符串中的每个空格替换成“%20”。例如，当字符串为We Are Happy.则经过替换之后的字符串为We%20Are%20Happy.
### `Approach 1`
假如允许申请新的内存，先将字符串复制到缓存，然后根据缓存边写回原字符串内存边替换空格

**Complexity Analysis**

-   Time Complexity: $O(n)$
### `Approach 2`
替换一次空格就往后移动一次字符串

**Complexity Analysis**

-   Time Complexity: $O(n^2)$

### `Approach 3`
先统计字符串中的空格，计算出替换后的字符串结束符'\0'的位置，然后**从后向前**地替换掉空格

**Complexity Analysis**

-   Time Complexity: $O(n)$
### 4.  从尾到头打印链表
***
输入一个链表，按链表值从尾到头的顺序返回一个ArrayList
### `Approach 1`
遍历链表，通过修改节点的指针翻转链表，然后再输出（**会修改链表结构**）

**Complexity Analysis**

-   Time Complexity: $O(n)$
### `Approach 2`
遍历链表，将节点压入堆栈后输出（**需要额外的数据结构与内存空间**）

**Complexity Analysis**

-   Time Complexity: $O(n)$

### `Approach 3`
先遍历链表，获取链表长度。然后申请对应长度的数组，再遍历链表，从后向前将节点值写入数组（**需要额外的数据结构与内存空间**）

**Complexity Analysis**

-   Time Complexity: $O(n)$  
### 5.  重建二叉树
***
输入某二叉树的前序遍历和中序遍历的结果，请重建出该二叉树。假设输入的前序遍历和中序遍历的结果中都不含重复的数字。例如输入前序遍历序列{1,2,4,7,3,5,6,8}和中序遍历序列{4,7,2,1,5,3,8,6}，则重建二叉树并返回。
### `Approach 1`
- 前序遍历序列中，第一个数字总是树的根节点，接下来是左子树的节点组成的序列，最后是右边是右子树的节点组成的序列
- 中序遍历序列中，树的根节点的左边是左子树的节点组成的序列，右边是右子树的节点组成的序列
- 前序遍历序列与中序遍历序列长度一样

根据以上两点，可以先从前序遍历序列获取根节点的值，然后扫描中序遍历序列获取根节点的位置，计算左右子树的节点数量，从而得到左右子树的前序遍历序列和
**Complexity Analysis**

-   Time Complexity: $O(n)$

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MDAxMjg2NTYsMTY4NTAwMTQ2NiwyMT
M0NzI4OTU0LC0yOTg2MDI1ODcsMTU1MDA0NjAxOF19
-->