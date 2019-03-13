# 安装步骤
1. 下载nginx压缩包  解压tar –zxvf -C /xxx解压到指定临时安装目录
2. mkdir -p /usr/local/nginx 创建安装目录
3. 安装依赖:
<br>
   yum -y install gcc gcc-c++ autoconf automake make
   yum -y install zlib zlib-devel openssl openssl-devel pcre pcre-devel
4. 进入到解压目录
5. 指定openssl目录 ./configure --with-openssl=/usr/bin/openssl
6. 执行编译和安装命令 make && make install prefix=/usr/local/nginx
7. 进入安装目录的sbin下(/usr/local/nginx/sbin)
8. 启动nginx ./nginx -c /usr/local/nginx/conf/nginx.conf

链接地址:
<br/>
https://blog.csdn.net/tangyaliang11/article/details/78675535
https://blog.csdn.net/yougoule/article/details/78186138
