# 安装步骤
1. 创建redis安装目录(mkdir -p /usr/local/redis/etc);
2. tar –zxvf -C <target folder>解压到指定临时目录;
3. 进入解压目录,执行make命令 ;
4. cd src;
5. make install PREFIX=/usr/local/redis;
6. 复制配置文件,在解压目录下有一个redsis.config文件,复制到/usr/local/redis/etc目录下;

# Redis 配置文件
* 设置外网访问
在 Linux 中安装了Redis 服务，当在客户端通过远程连接的方式连接时，报could not connect错误。
错误的原因很简单，就是没有连接上redis服务，由于redis采用的安全策略，默认会只准许本地访问。
需要通过简单配置，完成允许外网访问。  
修改redis的配置文件，将所有bind信息全部屏蔽。  
#&nbsp;bind 192.168.1.100 10.0.0.1  
#&nbsp;bind 192.168.1.8  
#&nbsp;bind 127.0.0.1  

* 设置密码
* 配置文件修改 requirepass Bdsk@123;
* 命令修改临时生效 config set requirepass Bdsk@123;

* 端口开放
修改Linux的防火墙(iptables),开启你的redis服务端口,redis默认是6379。
命令：/sbin/iptables -I INPUT -p tcp --dport 6379 -j ACCEPT
保存防火墙修改命令：/etc/rc.d/init.d/iptables save
不出意外的话，现在就可以在程序中远程访问远程主机上的redis server了

* 设置为守护进程
daemonize yesdaemonize yes

修改完成后需要重新启动redis服务。

# Redis命令
首先进入redis的bin目录
* 启动
./redis-server < redis etc config path >
* client连接
./redis-client -h < host > -p < port > -a < password >
