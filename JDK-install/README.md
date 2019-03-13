# 安装步骤
1. tar –zxvf dk-8u131-linux-x64.tar.gz 解压缩
2. vi etc/profile加入内容如下：
	export JAVA_HOME=/usr/local/jdk1.8.0_131
	export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
	export PATH=$JAVA_HOME/bin:$PATH
4.	source /etc/profile    生效配置文件
5.	java –version 查看版本 
6.	javac 查看编译命令是否正常
