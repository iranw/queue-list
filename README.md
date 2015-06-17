### beanstalkd 与 rabbitmq功能&性能对比

![beanstalkd rabbitmq对比图](https://raw.githubusercontent.com/iranw/queue-list/master/rabbitmqvsbeanstalkd.png)

##### 功能对比图
| Item                 |     RabbitMQ |     Beanstalkd |
| :--------------------|-------------:|---------------:|
| 持久化               |          Yes |           Yes  |
| 分布式               |          Yes |           Yes  |
| 高可用               |          Yes |            No  |
| 路由定制             |          Yes |            No  |
| Get定制              |          Yes |            No  |
| 认证                 |          Yes |            No  |
| 管理客户端           |     自带(强) |     第三方(弱) |
| 双向解耦(RPC)        |          Yes |            No  |
| php扩展              |          Yes |    Yes(弱 bug) |

##### 性能对比图
| Item                 |     RabbitMQ |     Beanstalkd |
| :--------------------|-------------:|---------------:|
| QPS(多连SET)         |          106 |           930  |
| QPS(单连多SET)       |         6210 |          3240  |

>`注`：从目前测试结果来看，在建立连接+队列操作+销毁连接这个过程beanstalkd效率还是比较高的。但是一次连接多次操作队列，rabbit则胜于beanstalkd。可见rabbitmq性能损失是在建立连接方面

[^demo]:发散思想:如果使用rabbitmq来做队列服务，同时又想提升性能，我们使用rabbitmq连接池来减少连接性能损失

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
感谢阅读这份测试文档。如果对您有用或者以后可能用的上的话。请点个`赞`，轻轻一点是对作者最大的支持

