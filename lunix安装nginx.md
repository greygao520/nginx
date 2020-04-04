lunix安装nginx

##### 一、安装nginx

1. 安装make：

```shell
yum -y install gcc automake autoconf libtool make
```

2. 安装g++：

```shell
yum -y install gcc gcc-c++
```

3. 安装所需依赖

```shell
yum -y install zlib zlib-devel openssl openssl--devel pcre pcre-devel
```

4. 下载nginx

```shell
 sudo wget  http://nginx.org/download/nginx-1.13.3.tar.gz
```

5. 新建目录：

```shell
 sudo mkdir  /usr/local/nginx
```

6. 将ngnix移动至新建目录下：

```shell
sudo mv nginx-1.13.3.tar.gz /usr/local/ngnix/
```

7. 进入到新建的目录下，解压缩：

```shell
  cd /usr/local/nginx
  sudo tar -zxvf nginx-1.13.3.tar.gz
```

8. 进入到nginx-1.13.3目录，进行安装：

```shell
./configure --prefix=/usr/local/nginx
## 安装到/usr/local/nginx的nginx目录下
make
make install
```

9. 安装完成

   ```shell
   Configuration summary
     + using system PCRE library
     + OpenSSL library is not used
     + using system zlib library
   
     nginx path prefix: "/usr/local/nginx"
     nginx binary file: "/usr/local/nginx/sbin/nginx"
     nginx modules path: "/usr/local/nginx/modules"
     nginx configuration prefix: "/usr/local/nginx/conf"
     nginx configuration file: "/usr/local/nginx/conf/nginx.conf"
     nginx pid file: "/usr/local/nginx/logs/nginx.pid"
     nginx error log file: "/usr/local/nginx/logs/error.log"
     nginx http access log file: "/usr/local/nginx/logs/access.log"
     nginx http client request body temporary files: "client_body_temp"
     nginx http proxy temporary files: "proxy_temp"
     nginx http fastcgi temporary files: "fastcgi_temp"
     nginx http uwsgi temporary files: "uwsgi_temp"
     nginx http scgi temporary files: "scgi_temp"
   ```

   10. 执行完成后，在新建的文件夹下，会有 `conf`, `hmtl`, `sbin` 等文件夹：

   ![image-20200404145520794](C:\Users\GreyGao\AppData\Roaming\Typora\typora-user-images\image-20200404145520794.png)  

​     

##### 二、启动、重启、暂停nginx

a. 启动执行：

```shell
    sudo /usr/local/nginx/sbin/nginx
```

成功如下图：
![img](https://img2018.cnblogs.com/blog/846711/201905/846711-20190522212938287-1627540341.png)

b. 重启：

```shell
    sudo /usr/local/nginx/sbin/nginx -s reload
```

c. 暂停：

```shell
    sudo /usr/local/nginx/sbin/nginx -s stop
```

##### 三、开启阿里云服务80端口访问

可以修改nginx监听的端口

```shell
vim /usr/local/nginx/conf/nginx.conf
```

![image-20200404152259922](C:\Users\GreyGao\AppData\Roaming\Typora\typora-user-images\image-20200404152259922.png)

