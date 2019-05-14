## MySQL学习心得

### 名词定义

- **冗余**：存储两倍数据，冗余降低了性能，但提高了数据的安全性。
- **主键**：主键的值是唯一的。
- **外键：**外键用于关联两个表。
- **复合键**：复合键（组合键）将多个列作为一个索引键，一般用于复合索引。

### MySQL安装与启动

* Mac安装：
  * 安装
  * 设置打开MySQL服务
  * vim ~/.bash_profile  PATH=$PATH:/usr/local/mysql/bin
  * source ~/.bash_profile
* 启动：mysql -u root -p

### 基础语法

* 创建数据库：CREATE DATABASE 数据库名；

* 删除数据库：DROP DATABASE 数据库名；

* 使用数据库：USE 数据库名；

* 建表：CREATE TABLE TABLE_NAME (column_name column_type);

* 删表：DROP TABLE TABLE_NAME;

* 留表删记录：TRUNCATE TABLE TABLE_NAMEe;

* 留表删数据：DELETE FROM TABLE_NAME WHERE CONDITION;

* 增加数据：INSERT INTO TABLE_NAME (FILED) VALUES (VALUE1);

* 读表:SELECT COLUMN_NAME FROM TABLE_NAME;

* 查表:

  ```
  SELECT column_name,column_name
  FROM table_name
  [WHERE Clause]
  [LIMIT N][ OFFSET M]
  ```
  
* WHERE子句：

  ```
  SELECT field1, field2,...fieldN FROM table_name1, table_name2...
  [WHERE condition1 [AND [OR]] condition2.....
  ```

  * MySQL 的 WHERE 子句的字符串比较是不区分大小写的。 但可以使用 BINARY 关键字来设定 WHERE 子句的字符串比较是区分大小写的。
	```
	SELECT * from runoob_tbl WHERE BINARY 		runoob_author='runoob.com';
	```

* 改表数据内容：UPDATE

* ```
  UPDATE table_name SET field1=new-value1, field2=new-value2
  [WHERE Clause]
  ```

* DELETE语句：

  ```
  DELETE FROM table_name [WHERE Clause]
  ```

* LIKE语句（如果没有使用百分号 **%**, LIKE 子句与等号 **=** 的效果是一样的。）：

  ```
  SELECT field1, field2,...fieldN 
  FROM table_name
  WHERE field1 LIKE condition1 [AND [OR]] filed2 = 'somevalue'
  ```

* UNION语句(多个SELECT语句会删除重复的数据)

  ```
  SELECT expression1, expression2, ... expression_n
  FROM tables
  [WHERE conditions]
  UNION [ALL | DISTINCT]
  SELECT expression1, expression2, ... expression_n
  FROM tables
  [WHERE conditions];
  
  // DISTINCT: 可选，删除结果集中重复的数据。默认情况下 UNION 操作符已经删除了重复数据，所以 DISTINCT 修饰符对结果没啥影响。
  
  // ALL: 可选，返回所有结果集，包含重复数据。
  ```

* **ORDER BY**排序

* ```
  SELECT field1, field2,...fieldN table_name1, table_name2...
  ORDER BY field1, [field2...] [ASC [DESC]]
  ```

* **GROUP BY**对结果进行分组

  ```
  SELECT column_name, function(column_name)
  FROM table_name
  WHERE column_name operator value
  GROUP BY column_name;
  ```

  * With rollup 对分组结果进行汇总

  * ```
    SELECT name, SUM(singin) as singin_count FROM  employee_tbl GROUP BY name WITH ROLLUP;
    ```

  * 用coaleace对WITH ROLLUP的NULL值进行可视化处理

  * ```
    SELECT coalesce(name, '总数'), SUM(singin) as singin_count FROM  employee_tbl GROUP BY name WITH ROLLUP;
    ```

* 

### 数据类型

* 数值：
  * INT
  * FLOAT
  * DOUBLE
  * DECIMAL
* 时间：
  * DATE
  * TIME
  * YEAR
  * DATETIME
  * TIMESTAMP
* 字符串：
  * CHAR
  * VARCHAR

### 特殊案例

* 将 id 为 5 的手机号改为默认的 **-** : update students settel=default where id=5;

* 将所有人的年龄增加 1: update students set age = age+1;

* 将手机号为 13288097888 的姓名改为 "小明", 年龄改为 19: update students set name="小明", age=19 where tel="13288097888";

* 将字段中的特定字符串批量修改为其他字符串时，可已使用以下操作：

  ```
  UPDATE table_name SET field=REPLACE(field, 'old-string', 'new-string') 
  [WHERE Clause]
  ```

* 以下实例将更新 runoob_id 为 3 的runoob_title 字段值的 "C++" 替换为 "Python"：

  ```
  UPDATE runoob_tbl SET runoob_title = REPLACE(runoob_title, 'C++', 'Python') where 
  runoob_id = 3;
  ```

* Like模糊匹配查询：

  ```
  '%a'     //以a结尾的数据
  'a%'     //以a开头的数据
  '%a%'    //含有a的数据
  '_a_'    //三位且中间字母是a的
  '_a'     //两位且结尾字母是a的
  'a_'     //两位且开头字母是a的
  ```

### 回顾

* 周五晚上学了一会，感觉还挺简单，再复杂的查询语句，无非是多层条件的嵌套罢了，因此查询并不难。
* 学到后面开始教事务，那基本和我没什么关系了，不至于让我RollBack吧。
* 今天把之前的查询条件复习了一遍，整理了这一份文档，如果有需要的话查文档会更快一些。