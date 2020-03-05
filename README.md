# docker-ngixn
docker + nginx + wordpress , to build a personal blog website
<br>
Environmental dependence: docker
<br>
Instructions:<br>
Copy the entire folder to the desired directory<br>
Configure `docker-compose.yml` file, modify environment variables, set password<br>
Go into the directory and run `docker-compose up -d`<br>
Wait for the end of the run, run `docker-compose ps` to see the docker process<br>

You may see something like that:
```
      Name                    Command               State                    Ports                  
----------------------------------------------------------------------------------------------------
web_mysql_1        docker-entrypoint.sh mysqld      Up      3306/tcp                                
web_nginx_1        nginx -g daemon off;             Up      0.0.0.0:443->443/tcp, 0.0.0.0:80->80/tcp
web_phpmyadmin_1   /docker-entrypoint.sh apac ...   Up      0.0.0.0:8080->80/tcp                    
web_wordpress_1    docker-entrypoint.sh php-fpm     Up      9000/tcp 
```