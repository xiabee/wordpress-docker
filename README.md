# docker-ngixn

docker + nginx + wordpress , to build a personal blog website
<br>
Environmental dependence: docker
<br>
**HTTP Website Configuration Description:**

Copy the entire folder to the required directory (including the `nginx` folder and the `nginx. conf` in it) 

Delete `nginx_https.conf` in the `nginx` folder`

Configure the `docker compose.yml` file, modify the environment variables, and set the password

Enter the directory and run ` docker compose up-d`

Wait for the end of running, run 'docker compose PS' to view the docker process

Note `nginx. conf` in the `nginx` folder. Make sure it exists. This is the key to the server's work.



**HTTPS Website Configuration Description:**

Repeat the above operation, upload the certificate file to the host computer's folder`./ nginx`, configure the file `nginx_https. conf`, delete `nginx.conf`,and restart docker



***

docker + nginx +mysql + wordpress 一键式搭建个人博客
环境依赖：docker
<br>

**http 网站配置说明：**

将整个文件夹复制到所需目录（包括`nginx`文件夹和里面的`nginx.conf`）<br>

删除`nginx`文件夹里面的`nginx_https.conf`

配置`docker compose.yml`文件，修改环境变量，设置密码

进入目录并运行`docker compose up-d`

等待运行结束，运行`docker compose ps`查看docker进程

注意`nginx`文件夹中的`nginx.conf`，确保它存在，这是服务器工作的关键。



**https 网站配置说明：**

重复以上操作，，将证书文件上传至宿主机`./nginx`文件夹，配置`nginx_https.conf`文件,删除`nginx.conf`，重启docker

***

如果正常运行的话，输入`docker-compose ps`应该能看到这个：
```
      Name                    Command               State                    Ports                  
----------------------------------------------------------------------------------------------------
web_mysql_1        docker-entrypoint.sh mysqld      Up      3306/tcp                                
web_nginx_1        nginx -g daemon off;             Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/tcp
web_phpmyadmin_1   /docker-entrypoint.sh apac ...   Up      0.0.0.0:8080->80/tcp                    
web_wordpress_1    docker-entrypoint.sh php-fpm     Up      9000/tcp 
```

