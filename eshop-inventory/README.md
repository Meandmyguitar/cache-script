1、线程池+内存队列初始化

2、两种请求对象封装

3、请求异步执行Service封装

4、请求处理的工作线程封装

5、两种请求Controller接口封装

6、读请求去重优化

如果一个读请求过来，发现前面已经有一个写请求和一个读请求了，那么这个读请求就不需要压入队列中了

因为那个写请求肯定会更新数据库，然后那个读请求肯定会从数据库中读取最新数据，然后刷新到缓存中，自己只要hang一会儿就可以从缓存中读到数据了

7、空数据读请求过滤优化