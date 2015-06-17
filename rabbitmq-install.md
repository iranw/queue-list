# ubuntu 安装 RabbitMQ 服务


###### 1、安装编译环境
```
#apt-get install build-essential openssl libncurses5-dev unixodbc-dev libssl-dev
```


###### 2、安装erlang软件
* 下载页面：[http://www.erlang.org/download.html](http://www.erlang.org/download.html)
* 下载版本：[http://www.erlang.org/download/otp_src_17.5.tar.gz](http://www.erlang.org/download/otp_src_17.5.tar.gz)


###### 3、编译安装
```
#./configure --prefix=/usr/local/erlang --enable-hipe --enable-threads --enable-smp-support --enable-kernel-poll  --without-javac
#make
#make install
```

###### 4、环境设置
```
#ln -s /usr/local/erlang/bin/erl /usr/local/bin/erl
```
* 另外在/etc/profile 文件添加代码
```
#vim /etc/profile
export PATH=$PATH:/usr/local/erlang/bin/ #保存退出vim
#source /etc/profile
```


###### 5、下载rabbitMQ二进制包
* 下载地址:[https://www.rabbitmq.com/download.html](https://www.rabbitmq.com/download.html)
* [https://www.rabbitmq.com/releases/rabbitmq-server/v3.5.3/rabbitmq-server-generic-unix-3.5.3.tar.gz](https://www.rabbitmq.com/releases/rabbitmq-server/v3.5.3/rabbitmq-server-generic-unix-3.5.3.tar.gz)


###### 6、文件解压到/usr/local/文件夹
```
#tar -zxvf rabbitmq-server-generic-unix-3.5.3.tar.gz
#cp -rf rabbitmq_server-3.5.3 /usr/local/
```


###### 7、添加环境变量
```
#vim /etc/profile
export PATH=$PATH:/usr/local/rabbitmq_server-3.5.3/sbin/    #保存退出vim
#source /etc/profile
```

###### 8、开启web管理工具
```
#rabbitmq-plugins enable rabbitmq_management    #开启管理插件
#rabbitmqctl stop                               #关闭
#rabbitmq-server start                          #启动服务器
```

###### 9、创建用户
```
#rabbitmqctl add_user admin 123456
#rabbitmqctl set_user_tags admin administrator
#rabbitmqctl set_permissions -p / admin ".*" ".*" ".*"
```
`注`:默认的guest无法登录，需要创建新的用户

###### 10、重启rabbitmq服务器
```
#rabbitmqctl stop
#rabbitmq-server start
```

客户端地址：[http://localhost:15672](http://localhost:15672)

友情链接
* [beanstalkd安装手册](https://github.com/iranw/queue-list/blob/master/beanstalkd-install.md)
* [beanstalkd VS rabbitMQ 功能对比](https://github.com/iranw/queue-list)

---------
感谢阅读这份帮助文档。如果对您有用或者以后可能用的上的话。请点个`赞`，轻轻一点是对作者最大的支持