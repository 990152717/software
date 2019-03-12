安装流程
1. [RPM源包下载](https://dev.mysql.com/downloads/repo/yum/)
2. sudo yum localinstall platform-and-version-specific-package-name.rpm 安装rpm
3. sudo yum install mysql-community-server 安装mysql
4. sudo service mysqld start 启动mysql
5. sudo service mysqld status 查看状态
6. sudo grep 'temporary password' /var/log/mysqld.log（查看初始密码）
7. mysql -hhost -uroot –pxxx    登录mysql
8. LTER USER 'root'@'localhost' IDENTIFIED BY “password” 修改密码

命令行执行sql
D:\mysql\bin\mysql –uroot –p123456 -Dtest<d:\test\ss.sql
source [sql脚本文件的路径全名] 或 Mysql>\. [ql脚本文件的路径全名]
示例source d:\test\ss.sql 或者 \. d:\test\ss.sql

修改外网访问：
1.mysql> use mysql;
2.mysql> update user set host='%' where user='root';
3.mysql> flush privileges;

查看mysql启动失败原因	
systemctl status mysqld.service
