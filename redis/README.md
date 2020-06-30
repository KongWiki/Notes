# Redis

## 数据类型&操作

### String

|      可以存储的值      |                             操作                             |
| :--------------------: | :----------------------------------------------------------: |
| 字符串, 整数或者浮点数 | 对整个字符串或者字符串的其中一部分执行操作, 对整数和浮点数执行自增或者自减操作 |

![String](https://i.loli.net/2020/06/29/3HgbN5azTZ7YU6I.png)

```shell
> set hello world
> get hello 
"world"
> del hello
(integer 1)
> get hello 
(nil)
```





### List

| 可以存储的值 |                             操作                             |
| :----------: | :----------------------------------------------------------: |
|     列表     | 从两端压入或者弹出元素, 对单个或者多个元素进行修剪, 只保留一个范围内的元素 |

![List](https://i.loli.net/2020/06/29/aKjbBSLtIE64Nqn.png)



```shell
> rpush list-key item
(integer) 1
> rpush list-key item2
(integer) 2
> rpush list-key item
(integer) 3

> lrange list-key 0 -1
1) "item"
2) "item2"
3) "item"

> lindex list-key 1
"item2"

> lpop list-key
"item"

> lrange list-key 0 -1
1) "item2"
2) "item"
```



### Set

| 可以存储的值 |                             操作                             |
| :----------: | :----------------------------------------------------------: |
|   无序集合   | 添加, 获取, 移除单个元素, 检查一个元素是否存在于集合中, 计算交集, 并集, 差集, 从集合里面随机获取元素(元素不重复) |

![Set](https://i.loli.net/2020/06/29/vZtX2CVQSbkgBzu.png)

```shell
> sadd set-key item
(integer) 1
> sadd set-key item2
(integer) 1
> sadd set-key item3
(integer) 1
> sadd set-key item
(integer) 0

> smembers set-key
1) "item"
2) "item2"
3) "item3"

> sismember set-key item4
(integer) 0
> sismember set-key item
(integer) 1

> srem set-key item2
(integer) 1
> srem set-key item2
(integer) 0

> smembers set-key
1) "item"
2) "item3"
```



### ZSet

| 可以存储的值 |                             操作                             |
| :----------: | :----------------------------------------------------------: |
|   有序集合   | 添加, 获取, 移除元素, 根据分值范围或者成员来获取元素, 计算一个键的排名 |

![ZSet](https://i.loli.net/2020/06/29/wkTNSHu16B25ejv.png)

```shell
> zadd zset-key 728 member1
(integer) 1
> zadd zset-key 982 member0
(integer) 1
> zadd zset-key 982 member0
(integer) 0

> zrange zset-key 0 -1 withscores
1) "member1"
2) "728"
3) "member0"
4) "982"

> zrangebyscore zset-key 0 800 withscores
1) "member1"
2) "728"

> zrem zset-key member1
(integer) 1
> zrem zset-key member1
(integer) 0

> zrange zset-key 0 -1 withscores
1) "member0"
2) "982"
```



### Hash

| 可以存储的值 |                             操作                             |
| :----------: | :----------------------------------------------------------: |
|    哈希表    | 添加, 获取, 删除元素, 根据分值范围或者成员来获取元素, 计算一个键的排名 |

![Hash](https://i.loli.net/2020/06/29/Qab9lNYhzDKRF3m.png)

```shell
> hset hash-key sub-key1 value1
(integer) 1
> hset hash-key sub-key2 value2
(integer) 1
> hset hash-key sub-key1 value1
(integer) 0

> hgetall hash-key
1) "sub-key1"
2) "value1"
3) "sub-key2"
4) "value2"

> hdel hash-key sub-key2
(integer) 1
> hdel hash-key sub-key2
(integer) 0

> hget hash-key sub-key1
"value1"

> hgetall hash-key
1) "sub-key1"
2) "value1"
```





## Hash表的实现逻辑



## 使用场景

### 计数器

### 缓存

### 查找表

### 消息队列

### 会话缓存

### 分布式锁实现