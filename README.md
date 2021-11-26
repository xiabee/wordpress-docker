# Wordpress-Docker

* `nginx` + `mariadb `+ `wordpress`一键式搭建个人博客服务

* 环境依赖：`docker`

  ```bash
  sudo apt install docker docker-compose
  ```

  

## 更新说明

* `PHP`版本更新至`8.0`
* `Wordpress`版本更新至`5.8.1`



## Http 网站配置说明

```bash
git clone https://github.com/xiabee/wordpress-docker.git
cd wordpress-docker
rm nginx/nginx_https.conf
docker-compose up -d
```



* 将整个文件夹复制到所需目录（包括`nginx`文件夹和里面的`nginx.conf`）<br>

* 删除`nginx`文件夹里面的`nginx_https.conf`

* 配置`docker-compose.yml`文件，修改环境变量，设置密码

* 进入目录并执行命令`docker-compose up -d`



## Https 网站配置说明

* 需要有`可控域名`+`SSL证书`

```bash
git clone https://github.com/xiabee/wordpress-docker.git
cd wordpress-docker
rm nginx/nginx.conf
docker-compose up -d
```



* 将证书文件上传至宿主机`./nginx`文件夹
* 删除`nginx.conf`
* 配置`nginx_https.conf`文件，修改证书对应的路径
* 配置`docker-compose.yml`文件，修改环境变量，设置密码
* 进入目录并执行命令`docker-compose up -d`



## 运行结果

* 如果正常运行的话，输入`docker-compose ps`应该能看到这个：

```
      Name                    Command               State                    Ports                  
-----------------------------------------------------------------------------
web_mysql_1        docker-entrypoint.sh mysqld      Up      3306/tcp                                
web_nginx_1        nginx -g daemon off;             Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/t
web_wordpress_1    docker-entrypoint.sh php-fpm     Up      9000/tcp 
```



* 浏览器访问`ip`或域名会跳转到`wordpress`的安装界面：

  ![](https://tva1.sinaimg.cn/large/0084b03xly1gwdl0zor35j31890ql79w.jpg)



## 附：其他相关命令

```bash
docker-compose restart
# 重启容器
docker-compose stop
# 停止容器
docker-compose down
# 停止并删除容器
docker-compose ps
# 查看容器运行状态
```



代码详解和故障排除过程看这里：[https://blog.xiabee.cn/posts/wordpress-docker](https://blog.xiabee.cn/posts/wordpress-docker)

