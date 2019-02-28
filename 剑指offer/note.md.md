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
扫描数组，当扫描到下标为$i$的数字$a_i$时，设$a_i=m$，如果$a_i=i$则扫描下一个；如果$a_i \ne i$，判断$a_i$是否与$a_m$相等。如果$a_i=a_m$，那么$a_i$就是要找的数；如果$a_i \ne a_m$则1交换$a_i$与$a_m$，继续扫描下一个
**Complexity Analysis**

-   Time Complexity: $O(n)$
-   Space Complexity:  $O(1)$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NDQ4MDg0OTYsMTI4ODkwMjY4NF19
-->