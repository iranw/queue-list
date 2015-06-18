# 队列镜像的使用

镜像地址:[http://pan.baidu.com/s/1kTio79X](http://pan.baidu.com/s/1kTio79X)

本镜像包含软件
* Ubuntu 14.04.2 LTS
* beanstalkd 1.9
* Erlang/OTP 17
* RabbitMQ 3.5.3

###诗经镜像步骤

###### 1、将镜像导入docker
```
#docker load --input queue.tar
```
`注`：docker自行google安装

###### 2、启动镜像
```
# docker run -idt -p 5672:5672 -p 15672:15672 -p 11300:11300 queue:v3
```

###### 3、进入系统启动服务
```
# docker ps
# docker attach a1d2276cf104        #进入终端
# /etc/init.d/beanstalkd start      #启动beanstalkd服务
# source /etc/profile
# rabbitmq-server start&            #启动rabbitmq队列服务
```


######