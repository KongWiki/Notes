## MySQL 笔记

### where

1. 后面可接某个字段的具体值

   ```sql
   SELECT population FROM world
     WHERE name = 'France'
   ```

   

2. in 

   ```sql
   SELECT name, population FROM world
     WHERE name IN ('Brazil', 'Russia', 'India', 'China');
   ```

3. between

   ```sql
   SELECT name, area FROM world
     WHERE area BETWEEN 250000 AND 300000
   ```

4. or 和 xor

   ```sql
   /*or 或运算*/
   SELECT name, population, area FROM world
    WHERE area>3000000 or population >250000000;
    
   /*xor  逻辑异或 两个条件相同（同真或同假）即为假（0），两个条件不同即为真（1）*/
   SELECT name, population, area FROM world
    WHERE area>3000000 XOR population >250000000; 
   ```

5. 模糊查询 like 

   ```sql
   SELECT name FROM world
    WHERE name like 'United%'
   ```

6. 

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

### 创建计算字段

* Concat()

  把多个串连接起来形成一个较长的串

### 易忘命令

* RTrim()

  去除右侧多余空格   

* LTrim()

  去除左侧多余空格

* Left

  返回字符串左边字符

* Locate

  找出串的一个子串

* SubString 

  返回子串的字符

* Upper/Lower

  返回大小写
  
* Round(number, decimal)

  * 将number四舍五入到decimal位

    ```sql
    SELECT ROUND(135.375, 2);
    /*135.38*/
    ```

* <>

  不等于

* 