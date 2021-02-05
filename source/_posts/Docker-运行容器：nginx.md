---
title: Docker 运行容器：nginx
urlname: Docker 运行容器：nginx
date: 2021-01-16 23:12:56
tags:
index_img:
---

Docker 运行容器：nginx

1跑容器

```
docker run \
--name nginx \
-p 9943:9943 \
-d \
nginx
```

2，进入容器，复制default.conf的内容出来,并做相应修改，保存为 .conf 后缀文件

用这个命令，把整个容器内的nginx目录复制出来 (New:) docker cp nginx:/etc/nginx /hardDisk/dockerData/ 

    server {
        listen          9943;
        server_name     localhost;
        
        location / {
            proxy_pass http://192.168.0.110:9000;
        }
    
        #listen       80;
        #listen  [::]:80;
        #server_name  localhost;
    
        #charset koi8-r;
        #access_log  /var/log/nginx/host.access.log  main;
    
        #location / {
        #    root   /usr/share/nginx/html;
        #    index  index.html index.htm;
        #}
    }

3,再次运行nginx容器，这次挂载conf目录

```
docker run \
--name nginx \
-p 9943:9943 \
-v /hardDisk/dockerData/nginx/conf:/etc/nginx/conf.d \
-d \
nginx
```



（new）

```
docker run \
--name nginx \
-p 9943:9943 \
-p 8080:8080 \
-v /hardDisk/dockerData/nginx/:/etc/nginx/ \
-d \
nginx
```





