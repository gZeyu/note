## RBAC
基于角色的权限访问控制（`Role-Based Access Control`）作为传统访问控制（自主访问，强制访问）的有前景的代替受到广泛的关注。在`RBAC`中，权限与角色相关联，用户通过成为适当角色的成员而得到这些角色的权限。这就极大地简化了权限的管理。

### RBAC0
`RBAC0`是`RBAC`中最基本的模型。在这个模型中，系统将权限赋予角色，再把角色赋予用户。用户和角色，角色和权限都是多对多的关系。用户拥有的权限等于他所有的角色持有权限之和。
```mermaid
graph LR
U[用户] --多对多--> R((角色)) 
R((角色)) --多对多--> P(权限)
```
个人博客网站的权限复杂度不高，`RBAC0`基本能满足个人博客网站的权限需求。
## 数据库设计
接下来根据`RBAC0`模型设计数据库。
### 关系模式
```
blog_user(id, username, password, nickname, email, phone_number, avatar, level, gmt_create, gmt_modified)
blog_role(id, name, gmt_create, gmt_modified)
blog_permission(id, description, gmt_create, gmt_modified)
blog_user_role(id, user_id, role_id, gmt_create, gmt_modified)
blog_role_permission(id, role_id, perm_id, gmt_create, gmt_modified)
```
### MySQL 建表语句
#### 用户表 
```sql
CREATE TABLE blog_user
(
    id           bigint(20) unsigned NOT NULL AUTO_INCREMENT,
    username     varchar(20)         NOT NULL,
    password     varchar(15)         NOT NULL,
    nickname     varchar(20)         NOT NULL,
    email        varchar(30)         NOT NULL,
    phone_number varchar(11)         NOT NULL,
    avatar       varchar(255)        NOT NULL,
    level        varchar(20)         NOT NULL,
    rights       varchar(20)         NOT NULL,
    gmt_create   datetime            NOT NULL,
    gmt_modified datetime            NOT NULL,
    PRIMARY KEY (id),
    KEY (username),
    KEY (nickname),
    KEY (email),
    KEY (phone_number)
) ENGINE = InnoDB
  DEFAULT CHARSET = utf8;
```
#### 角色表  
```sql
CREATE TABLE blog_role
(
    id   bigint(20) unsigned NOT NULL AUTO_INCREMENT,
    name varchar(20)         NOT NULL,
    PRIMARY KEY (id),
    KEY (name)
) ENGINE = InnoDB
  DEFAULT CHARSET = utf8;
```
#### 权限表  
```sql
CREATE TABLE blog_permission
(
    id          bigint(20) unsigned NOT NULL AUTO_INCREMENT,
    description varchar(20)         NOT NULL,
    PRIMARY KEY (id),
    KEY (description)
) ENGINE = InnoDB
  DEFAULT CHARSET = utf8;
```
  
#### 用户角色关联表  
```sql
CREATE TABLE blog_user_role
(
    id      bigint(20) unsigned NOT NULL AUTO_INCREMENT,
    user_id bigint(20) unsigned NOT NULL,
    role_id bigint(20) unsigned NOT NULL,
    PRIMARY KEY (id)
) ENGINE = InnoDB
  DEFAULT CHARSET = utf8;
```
#### 角色权限关联表  
```sql
CREATE TABLE blog_role_permission
(
    id            bigint(20) unsigned NOT NULL AUTO_INCREMENT,
    role_id       bigint(20) unsigned NOT NULL,
    permission_id bigint(20) unsigned NOT NULL,
    PRIMARY KEY (id),
    KEY (role_id),
    KEY (permission_id)
) ENGINE = InnoDB
  DEFAULT CHARSET = utf8;
```
## 参考
1. [RBAC权限管理模型](https://www.xiaoman.cn/detail/150)
2. [基于角色的访问控制RBAC的mysql表设计](https://blog.csdn.net/xiaoxiaodongxie/article/details/52400488)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMzI4MzgwNjgsMjk0ODczMSwtMTkxMD
M5MzMzLC01MjU1NjQ3MDksNDIxNDg5NDM1LDc2OTY2ODIzMCw5
NjU5NjA4NDEsLTQyNDEyNDIxMywtMTMwNjYyNjU1NiwtMzE4NT
A3NzksODgyMTI0OTY2LDIxMjEwMjc5LC0yMjgxNTY5ODEsLTE1
MzYwMzY0OTUsMjE2NzMyNTU0LDEyMjQ5OTAzNDZdfQ==
-->