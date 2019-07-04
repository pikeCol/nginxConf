# nginxConf
### 安装nginx
ubuntu 中直接
`
sudo apt-get install nginx
`
进行安装，但是这种安装对定制模块和插件不太友好，所以我推荐用源码安装。以CentOS为栗子：
```
yum -y install wget gcc gcc-c++ autoconf automake make zlib zlib-devel pcre-devel pcre
````
下载源码
```
wget http://nginx.org/download/nginx-1.12.2.tar.gz
```
解压和安装
```
tar -zxvf nginx-1.12.2.tar.gz
cd nginx-1.12.2/
 ./configure
 make && make install
```
自定义初始化需要用到 ./configure 。./configure --help 查看所有参数。

### 与客户端有关的配置
|    指令    | 说明 |
| ---------- | --- |
| clent_body_buffer_size |  设置读取客户端请求体的缓冲区大小。32位系统，x86-64系统设置8KB的缓冲区，其他64位系统为16KB。超出缓冲区会被写入临时文件 |
| client_body_temp_path       |  定义存储客户端请求的临时文件目录，最多可以定义3个子集目录 |
| client_body_timeout | 定义读取客户端请求超时时间，即两个连续的读操作之间的间隔，如果超时HTTP会抛出408错误 | 

