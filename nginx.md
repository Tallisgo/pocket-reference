# nginx

> 为了不将`dify`平台的裸ip 暴露给用户，需要给ip套一个域名，在这个背景下接触了nginx
do


## 安装

```bash
sudo apt update

sudo apt install nginx
```



## 使用

```bash
# 检查 nginx 配置文件是否有语法错误
sudo nginx -t

# 启动 nginx 服务
sudo service nginx start

# 停止 nginx 服务
sudo service nginx stop

# 重载 nginx 配置（无需重启服务）
sudo nginx -s reload

# 查看 nginx 运行状态
sudo service nginx status


```


## 配置文件

1. 默认加载 `/etc/nginx/modules-enabled/*.conf `这下面的文件，若需要加载其他路径下的文件，需要修改配置信息


```bash
sudo vim /etc/nginx/nginx.conf

# 修改: include /etc/nginx/sites-enabled/*;

: include /etc/nginx/vhost.d/*;
```