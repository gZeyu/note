
# 整数与IP地址间的转换
## 题目描述
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
##  输出描述
```
输出  
1 输出转换成10进制的IP地址  
2 输出转换后的IP地址
```
## 示例
**Input**
```
10.0.3.193
167969729
```
**put**
```
10.0.3.193
167969729
```
## Approach
### 思路
1. IP地址字符串转换成10进制的IP地址。以“.”作为分隔符将IP地址字符串分割，将得到的4个字符串分别转成整数并移位，然后累加得到10进制的IP地址。
2. 10进制的IP地址转换成IP地址字符串。通过位运算以每8位为单元分割10进制的IP地址，将得到的4个整数转字符串，再依次拼接得到转换后的IP地址字符串。
### Java Code
``` Java
import java.util.Scanner;

public class Main {

  public static void main(String[] args) {
    Scanner scanner = TEST ? new Scanner(INPUT) : new Scanner(System.in);
    while (scanner.hasNextLine()) {
      String str = scanner.nextLine();
      long value = Long.valueOf(scanner.nextLine());
      System.out.println(getIPValue(str));
      System.out.println(getIPString(value));
    }
    scanner.close();
  }

  private static long getIPValue(String str) {
    String[] numberString = str.split("\\.");
    long value = 0;
    for (String s : numberString) {
      value <<= 8;
      value += Integer.valueOf(s);
    }
    return value;
  }

  private static String getIPString(long value) {
    return String.valueOf((value & 0xff000000) >> 24) + '.' + ((value & 0x00ff0000) >> 16) + '.'
        + ((value & 0x0000ff00) >> 8) + '.' + (value & 0x000000ff);
  }

  private static final boolean TEST = true;
  private static final String INPUT = "10.0.3.193\n" + "167969729\n";
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYxNzQzMDU5NCwxNDExNDc3NTQ0LC0xMT
Y2OTk0NjMxLDE3NDI0MDg0MzgsLTUxMjc1OTE1Nl19
-->