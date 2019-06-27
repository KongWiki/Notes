## Mysql 笔记

### 限制

可以使用`LIMIT`进行限制查询数据

```sql
SELECT column FROM table LIMIT 5 
```

同时使用还可以选择从哪一行开始

```sql
SELECT column FROM table LIMIT 3,5
```

意思为从第三行开始的五行（第一个参数为开始行数，第二个参数为检索行数）

因不方便于理解MySQL5支持LIMT的另一种写法，`LIMI 4 OFFSET 3`即从第三行开始，检索四条数据。

### 排序检索

* `DESC` 降序
* `AESC`生序

```sql
SELECT column1, column2, from table order by column1 DESC;
```

