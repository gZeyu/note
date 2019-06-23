```sql
CREATE DATABASE blog;
CREATE TABLE blog_user (
  id bigint(20) unsigned NOT NULL AUTO_INCREMENT,
  username varchar(20) NOT NULL,
  password varchar(15) NOT NULL,
  nickname varchar(20) NOT NULL,
  email varchar(30) NOT NULL,
  phone_number varchar(11) NOT NULL,
  avatar varchar(255) NOT NULL,
  level varchar(20) NOT NULL,
  rights varchar(20) NOT NULL,
  gmt_create datetime NOT NULL,
  gmt_modified datetime NOT NULL,
  PRIMARY KEY (id),
  KEY (username),
  KEY (nickname),
  KEY (email),
  KEY (phone_number)
) ENGINE = InnoDB DEFAULT CHARSET = utf8;
CREATE TABLE international_telephone_code(
  id bigint(20) unsigned NOT NULL AUTO_INCREMENT,
  country varchar(255) NOT NULL,
  area varchar(255) NOT NULL,
  PRIMARY KEY (id)
) ENGINE = InnoDB DEFAULT CHARSET = utf8;
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTkzMzUyNDg1XX0=
-->