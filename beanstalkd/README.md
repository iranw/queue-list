ubuntu 安装 beanstalkd 服务
1、直接源码apt-get安装
sudo apt-get install beanstalkd

2、编辑/etc/default/beanstalkd
BEANSTALKD_LISTEN_ADDR=0.0.0.0 #测试使用后，正式环境不能开启监听所有ip
BEANSTALKD_LISTEN_PORT=11300   #监控的端口
BEANSTALKD_EXTRA="-b /var/lib/beanstalkd" #是否开启持久化 如果注释就不开启
START=yes   #是否开机启动

3、启动方式
#/etc/init.d/beanstalkd start   #方法1
#service beanstalkd start       #方法2
#/usr/bin/beanstalkd -l 0.0.0.0 -p 11300 -b /var/lib/beanstalkd     #方法3
注释：无法使用stop停止服务，可以直接kill进程停止

4、管理方式
a、使用chrome扩展管理：https://chrome.google.com/webstore/detail/beanstalkd-dashboard/dakkekjnlffnecpmdiamebeooimjnipm
b、使用php管理工具管理：https://github.com/jimbojsb/bstools


注：关于beanstalkd分布式，是采用客户端分布式路由的，服务器直接并不知道彼此存在，相互透明