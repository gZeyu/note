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
排序后扫描

**Complexity Analysis**

-   Time Complexity: $O(nlogn)$
-   Space Complexity:  $O(n)$
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTkzNTkxNjk2LDE1NTAwNDYwMThdfQ==
-->