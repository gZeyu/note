## RBAC
基于角色的权限访问控制（`Role-Based Access Control`）作为传统访问控制（自主访问，强制访问）的有前景的代替受到广泛的关注。在`RBAC`中，权限与角色相关联，用户通过成为适当角色的成员而得到这些角色的权限。这就极大地简化了权限的管理。

### RBAC0
`RBAC0`是`RBAC`中最基本的模型。在这个模型中，系统将权限赋予角色，再把角色赋予用户。用户和角色，角色和权限都是多对多的关系。用户拥有的权限等于他所有的角色持有权限之和。
```mermaid
graph LR
U[用户] --多对多--> R((角色)) 
R((角色)) --多对多--> P(权限)
```
## 参考
1. [用MySQL实现微博关注关系的方案分析](https://my.oschina.net/yonghan/blog/475588)
2. [用Redis实现微博关注关系的分析](https://www.cnblogs.com/JockChou/p/4643646.html)
3. [社交网络如何设计存储好友关系的数据库的？](https://www.zhihu.com/question/20216864/answer/92695981  )
4. [微博关注我、我关注你数据库该怎么设计](https://blog.csdn.net/u010098331/article/details/51445904)
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjQ3NzExMTI3LC0yMjgxNTY5ODEsLTE1Mz
YwMzY0OTUsMjE2NzMyNTU0LDEyMjQ5OTAzNDZdfQ==
-->