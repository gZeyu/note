# 139. Word Break

>  **Related Topics:** 贪心

There are  _N_  children standing in a line. Each child is assigned a rating value.
You are giving candies to these children subjected to the following requirements:

-   Each child must have at least one candy.
-   Children with a higher rating get more candies than their neighbors.

What is the minimum candies you must give?

**Example 1:**

**Input:** [1,0,2]
**Output:** 5
**Explanation:** You can allocate to the first, second and third child with 2, 1, 2 candies respectively.

**Example 2:**

**Input:** [1,2,2]
**Output:** 4
**Explanation:** You can allocate to the first, second and third child with 1, 2, 1 candies respectively. The third child gets 1 candy because it satisfies the above two conditions.
## Approach 1
### 思路
我们先来看一个例子，下面是一个ratings数组以及一个按满足题目要求的最优分配方案candies数组。观察两个数组并结合题意，我们可以得到以下结论：
$$ candies[i]=MAX(左侧严格递增数组长度, 右侧严格递减数组长度,1) $$
```
ratings: [1 2 3 4 5 3 2 1 2 6 5 4 3 3 2 1 1 3 3 3 4 2]
candies: [1 2 3 4 5 3 2 1 2 4 3 2 1 3 2 1 1 2 1 1 2 1]
```
故我们可以维护两个辅助数组分别记录左侧严格递增数组长度和右侧严格递减数组长度，然后根据上面的公式遍历两个辅助数组就可以得到最优分配方案。
```
ratings:   [1 2 3 4 5 3 2 1 2 6 5 4 3 3 2 1 1 3 3 3 4 2]
左侧严格递增:[
```
### Java Code
``` Java
class Solution {  
  
  public int candy(int[] ratings) {  
    int[] left2Right = new int[ratings.length];  
    int[] right2Left = new int[ratings.length];  
    left2Right[0] = 1;  
    for (int i = 1; i < ratings.length; i++) {  
      left2Right[i] = ratings[i] > ratings[i - 1] ? left2Right[i - 1] + 1 : 1;  
    }  
    right2Left[ratings.length - 1] = 1;  
    for (int i = ratings.length - 2; i > -1; i--) {  
      right2Left[i] = ratings[i] > ratings[i + 1] ? right2Left[i + 1] + 1 : 1;  
    }  
    int sum = 0;  
    for (int i = 0; i < ratings.length; i++) {  
      sum += left2Right[i] > right2Left[i] ? left2Right[i] : right2Left[i];  
    }  
    return sum;  
  }  
  
  public static void main(String[] args) {  
    Solution s = new Solution();  
    System.out.println(s.candy(new int[] {1, 0, 2}));  
    System.out.println(s.candy(new int[] {1, 2, 2}));  
    System.out.println(  
        s.candy(new int[] {1, 2, 3, 4, 5, 3, 2, 1, 2, 6, 5, 4, 3, 3, 2, 1, 1, 3, 3, 3, 4, 2}));  
  }  
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTExOTczNjk5NSwxODk3MTQ0NzM4XX0=
-->