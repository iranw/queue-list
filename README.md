### beanstalkd 与 rabbitmq功能对比

![beanstalkd rabbitmq对比图](https://raw.githubusercontent.com/iranw/queue-list/master/rabbitmqvsbeanstalkd.png)

| Item                          |              Value |              Value | Qty  |
| :-----------------------------|-------------------:|-------------------:| :--: |
| Computer                      |           1600 USD |           1600 USD |  5   |
| Phone                         |             12 USD |             12 USD |  12  |
| Pipe                          |              1 USD |              1 USD | 234  |


注:*目前队列性能测试是通过php来测试的，测试php的性能来间接测试队列服务的性能，不知道有没有方法工具直接测试服务性能的？如果哪位知道，不吝赐教*

rabbitmq毕竟是老牌队列服务，功能全面优于beansalkd。beanstalkd作为后起之秀，目前也有很多大多数公司在使用(淘宝使用ing中)。但是由于缺乏高可用等比较敏感的功能，还是有待进一步发展更新。


友情链接
* [rabbitmq安装手册](https://github.com/iranw/queue-list/blob/master/rabbitmq-install.md)
* [beanstalkd安装手册](https://github.com/iranw/queue-list/blob/master/beanstalkd-install.md)

感谢[@驼神]()指点

参考文档：
* [https://zh.wikipedia.org/zh-hans/CAP定理](https://zh.wikipedia.org/zh-hans/CAP%E5%AE%9A%E7%90%86)
* [http://www.douban.com/group/topic/11765014/](http://www.douban.com/group/topic/11765014/)


---------
感谢阅读这份测试文档。如果对您有用或者以后可能用的上的话。请点个`赞`，是对作者最大的支持

