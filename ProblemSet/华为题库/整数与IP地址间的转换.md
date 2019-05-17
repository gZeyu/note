
# 整数与IP地址间的转换

原理：ip地址的每段可以看成是一个0-255的整数，把每段拆分成一个二进制形式组合起来，然后把这个二进制数转变成  
一个长整数。  
举例：一个ip地址为10.0.3.193  
| 每段数字 | 相对应的二进制数   |
|--|--|
| 10 | 00001010 |
| 0 | 00000000 |
| 3 | 00000011 |
| 193 | 11000001 |
组合起来即为：00001010 00000000 00000011 11000001，转换为10进制数就是：167773121，即该IP地址转换后的数字就是它了。
## 输入描述
```
输入  
1 输入IP地址  
2 输入10进制型的IP地址
```
## 输出描述
```
输出  
1 输出转换成10进制的IP地址  
2 输出转换后的IP地址
```
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
eyJoaXN0b3J5IjpbOTcxMjEzNDIyLC01MTI3NTkxNTZdfQ==
-->