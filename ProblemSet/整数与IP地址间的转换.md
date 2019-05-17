
## 机器人的运动范围

地上有一个m行和n列的方格。一个机器人从坐标(0,0)的格子开始移动，每一次只能向左，右，上，下四个方向移动一格，但是不能进入行坐标和列坐标的数位之和大于k的格子。 例如，当k为18时，机器人能够进入方格(35,37)，因为3+5+3+7 = 18。但是，它不能进入方格(35,38)，因为3+5+3+8 = 19。请问该机器人能够达到多少个格子？

### `Approach 1`
本题可用回溯法解。以坐标(0,0)的格子作为起点，使用深度优先策略向上下左右进行递归搜索，搜索过程中使用一个布尔值矩阵来记录字符矩阵中元素的访问情况，防止对可到达的格子重复计数。当准备进入坐标(i,j)的格子时，先检查行坐标和列坐标是否越界、该格子的访问情况以及行坐标和列坐标的数位之和是否大于k，若行坐标和列坐标合法、该格子未曾访问过且行坐标和列坐标的数位之和大于k，则将布尔值矩阵对应的元素置为真，将可到达的格子数加1，然后依次进入上下左右4个相邻的格子；若行坐标和列坐标不合法或该格子已经访问过了或行坐标和列坐标的数位之和大于k，则回溯到父节点。当算法回溯到坐标(0,0)的格子时，就可以统计出可达到的格子数量
#### **Code**
- **python**
``` python
# -*- coding:utf-8 -*-
class Solution:
    def movingCount(self, threshold, rows, cols):
        visited = [False] * (rows * cols)
        return self.movingCountCore(threshold, rows, cols, 0, 0, visited)

    def movingCountCore(self, threshold, rows, cols, row, col, visited):

        if row < 0 or row >= rows or col < 0 or col >= cols or visited[
                row * cols + col] == True:
            return 0
        if self.getDigitSum(row) + self.getDigitSum(col) > threshold:
            return 0
        visited[row * cols + col] = True
        return 1 + self.movingCountCore(threshold, rows, cols, row + 1, col, visited) \
            + self.movingCountCore(threshold, rows, cols, row - 1, col, visited) \
            + self.movingCountCore(threshold, rows, cols, row, col + 1, visited) \
            + self.movingCountCore(threshold, rows, cols, row, col - 1, visited)

    def getDigitSum(self, num):
        sum = 0
        while (num != 0):
            sum = sum + num % 10
            num = num // 10
        return sum
```

#### **Complexity Analysis**

-   Time Complexity: 非多项式时间

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNjMzMzgwMjcsNzMwOTk4MTE2XX0=
-->