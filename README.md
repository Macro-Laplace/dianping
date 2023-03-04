### 店铺点评APP

`Spring Boot` `MySQL` `Redis` `MyBatis` 

- **项目描述**：
    一个类似大众点评的APP后台,实现了找店铺、写点评、看热评、点赞关注的完整业务

    ![img](https://pic.imgdb.cn/item/6402f9daf144a010076ab309.png)
    
    
    
    - 短信登录:使用 Redis实现分布式 Session,解决集群间登录态同步问题;使用Hash代替String存储用户信息，节约了内存的同时也方便对单字段进行修改
    
    - 店铺查询:将热点店铺的信息缓存到Redis中，降低了MySQL的压力，提高了约75%的查询性能
    
    - 优惠券秒杀:使用 Redis+Lua脚本实现库存预检,并通过 Stream队列实现订单的异步创建,解决了超卖问题、实现一人一单。相比传统数据库大幅度提高了秒杀性能