## SQLite参考资料
[sqlite学习](http://www.runoob.com/sqlite/sqlite-installation.html)
# SQLite的安装
#### ubantu linux上的安装
```sh
$ sudo apt-get install sqlite3
```








    
    
# SQLite数据类型

SQLite 数据类型是一个用来指定任何对象的数据类型的属性。SQLite 中的每一列，每个变量和表达式都有相关的数据类型。

### SQLite存储类

存储类型 |  描述
--------|----------|
NULL    | 空值
INTEGER | 值是一个带符号的整数
REAL    | 值是一个浮点数   为8字节
TEXT    | 值是一个文本字符串，使用数据库编码（UTF-8、UTF-16BE 或 UTF-16LE）存储。
BLOB    |  	值是一个 blob 数据，完全根据它的输入存储

### Date与Time数据类型

SQLite 没有一个单独的用于存储日期和/或时间的存储类，但 SQLite 能够把日期和时间存储为 TEXT、REAL 或 INTEGER 值。

存储类  |  日期格式
-------|---------|
TEXT   | 格式为 "YYYY-MM-DD HH:MM:SS.SSS" 的日期。
REAL   | 从公元前 4714 年 11 月 24 日格林尼治时间的正午开始算起的天数
INTEGER | 从 1970-01-01 00:00:00 UTC 算起的秒数。



# 创建数据库

sqlite3 的基本语法如下：
```sh
$ sqlite3 test.db   (test.db为创建的数据库名)
```
一旦数据库被创建可以使用**.databases**来检查它是否在数据库列表中，语法：
```sh
sqlite>.databases
```
使用**.quit**退出数据库（sqlite提示符）

```sh
sqlite>.quit
```
# 创建表

SQLite 的 CREATE TABLE 语句用于在任何给定的数据库创建一个新表。创建基本表，涉及到命名表、定义列及每一列的数据类型。

语法:
```sh
create table student(
  column1 datatype  PRIMARY KEY(one or more columns),
   column2 datatype,
   column3 datatype,
   .....
   columnN datatype,
);
```
使用 SQLIte 命令中的 .tables 命令来验证表是否已成功创建，该命令用于列出附加数据库中的所有表
```sh
sqlite>.table
```
# 删除表
SQLite 的 DROP TABLE 语句用来删除表定义及其所有相关数据、索引、触发器、约束和该表的权限规范。

    使用此命令时要特别注意，因为一旦一个表被删除，表中所有信息也将永远丢失。
    
语法:
```sh
drop table student;
```

# 向表中添加数据(insert into)

SQLite 的 INSERT INTO 语句用于向数据库的某个表中添加新的数据行

```sh
1. insert into student(column1, column2, column3, ... ) values(value1, value2, value3, ...);
```
如果表的全列都插入数据才可以省略列名
```sh
2. insert into student values(value1, value2, value3 ...);
```

# 删除数据(delete)
SQLite 的 DELETE 查询用于删除表中已有的记录。可以使用带有 WHERE 子句的 DELETE 查询来删除选定行，否则所有的记录都会被删除。

语法:
1.删除整个表
```sh
delete from student;
```
2.删除表中某一列或某一项
```sh
delete from student where age=20 and name="李四"; (删除年龄20名字是李四的)
```

# 更新（改）数据(update ...set)
 
SQLite 的 UPDATE 查询用于修改表中已有的记录。可以使用带有 WHERE 子句的 UPDATE 查询来更新选定行，否则所有的行都会被更新。
语法:

```sh
1. update student set name = "张三",age = 21;(修改学生表中所有记录的名字为张三，年龄为21)
```
```sh
2. update student set name = "王五" where stno = 10001; (将学号为10001的学生的名字改为王五)
```

# 查询数据(select)
SQLite 的 SELECT 语句用于从 SQLite 数据库表中获取数据，以结果表的形式返回数据。这些结果表也被称为结果集。

语法:
1. 全查
```sh
select*from student;
```
2. 列查询
```sh
select name, age from student;
```
3. 条件查询
```sh
select name from student where age = 20;
```
### distinct(消除重复记录)
SQLite 的 DISTINCT 关键字与 SELECT 语句一起使用，来消除所有重复的记录，并只获取唯一一次记录。

有可能出现一种情况，在一个表中有多个重复的记录。当提取这样的记录时，DISTINCT 关键字就显得特别有意义，它只获取唯一一次记录，而不是获取重复记录。

语法：
```sh
select distinct age from student where [condition];
```


# 表的修改(alter)

在 SQLite 中，除了重命名表和在已有的表中添加列，ALTER TABLE 命令不支持其他操作。
1. 重命名表
```sh 
alter table student rename to student123;
```
2. 添加列
```sh
alter table student add column sex char(1);
```
