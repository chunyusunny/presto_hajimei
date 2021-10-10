# presto_hajimei

HyperLogLog 算法在 Presto 的应用<br/>

1. 搜索 HyperLogLog 算法相关内容，了解其原理，写出 5 条
   HyperLogLog 的用途或大数据场景下的实际案例。<br/>
   HyperLogLog 简称 HLL,作用是能够提供不精确的去重计数。<br/>
   特点：<br/>
   ->能够使用极少的内存来统计巨量的数据，在 Redis 中实现的 HyperLogLog，只需要 12k 内存就能统计 2^64 个数据<br/>
   ->计数存在一定的误差，误差率整体较低，标准误差为 0.81%<br/>
   ->误差可以通过设置辅助计算因子进行降低<br/>
   原理：<br/>
   ->用 hash 函数将数据转为比特串，从地位往高位看，记录第一个 1 的位置<br/>
   ->分桶计算调和平均数<br/>
   ->代入估算公式计算元素的数量<br/>
   <br/>

   用途：<br/>
   ->统计 APP 或网页的日活月活<br/>
   ->统计注册 IP 数<br/>
   ->统计页面实时 UV 数<br/>
   ->统计在线用户数<br/>
   ->统计用户每天搜索不同词条的个数<br/>

2. 在本地 docker 环境或阿里云 e-mapreduce 环境进行 SQL 查询，
   要求在 Presto 中使用 HyperLogLog 计算近似基数。（请自行创
   建表并插入若干数据）<br/>
   ![E3B77AB5-20A0-4244-8C8F-4496B863131E](https://user-images.githubusercontent.com/11592423/136693286-899e65f0-f661-4f87-b1e8-ba9e5c5d209b.png)
![F0BD2AA2-A9FA-4174-8410-2060C2694FFA](https://user-images.githubusercontent.com/11592423/136693314-0cf0ebf0-9924-46bb-b31e-93bfdf7994e6.png)
![2B9D0A7D-4190-4782-830E-70DFD43A3216](https://user-images.githubusercontent.com/11592423/136693515-a356257e-7389-4db2-b2f6-ea37f7af67fb.png)

![1CF39341-F23B-497F-BAF6-B32F39BE6465](https://user-images.githubusercontent.com/11592423/136693417-efd1ce2d-1ff4-4fca-bb75-c99d1a85258a.png)

3. 学习使用 Presto-Jdbc 库连接 docker 或 e-mapreduce 环境，重
   复上述查询。（选做）<br/>
