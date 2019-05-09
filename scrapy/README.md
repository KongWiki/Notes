## scrapy

### 创建项目

```shell
scrapy startproject xxxx	
```

### 项目结构

![image](https://ws1.sinaimg.cn/large/b9f9be27gy1g2o7idwukfj20g507fq3r.jpg)

* items.py  # 定义爬取的结构
* ｍiddlewares.py # 爬取时的中间件
* pipelines.py # 定义数据管道
  * 清理HTML数据
  * 验证爬取数据，检查爬取字段
  * 查重并丢弃重复内容
  * 将爬取结果保存到数据库
* settings.py # 配置文件
* spiders # 方式爬虫的文件夹

## 创建Spider

```shell
scrapy genspider name domain		
```

* name 为爬虫的名字，唯一
* domain 为爬取的目标网站
* 

