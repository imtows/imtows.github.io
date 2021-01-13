---
title: Docker 运行容器：halo
urlname: Docker 运行容器：halo
date: 2021-01-13 23:14:23
tags:
index_img:
---

Docker 运行容器：halo

由于没有arm64版本的halo镜像，所以这里自己做个镜像



1下载jar包

https://github.com/halo-dev/halo/releases

2编辑Dockerfile文件，和 jar 包放在同一个目录下面

```
# VERSION 0.0.1
# Author: mdx
# 基础镜像使用java---目前好找到的适用于树莓派的jdk8
FROM arm64v8/openjdk:8u121-jre-alpine
# 作者
MAINTAINER mdx 
# VOLUME 指定了临时文件目录为/tmp。
# 其效果是在主机 /var/lib/docker 目录下创建了一个临时文件，并链接到容器的/tmp
VOLUME /tmp
# 将jar包添加到容器中并更名为app.jar
ADD halo-1.4.2.jar app.jar
# 运行jar包
ENTRYPOINT ["java","-jar","/app.jar"]
```

创建镜像(注意后面的 .

```
docker build -t mdx/halo_arm64:v1 .
```

4下载通用配置文件，然后编辑文件

```
curl -o /home/ubuntu/tmp/application.yaml  --create-dirs  https://dl.halo.run/config/application-template.yaml
```



5把下载的文件，放到挂在目录下，然后启动容器

```
docker run -it -d --name halo -p 8090:8090  \
-v /hardDisk/dockerData/halo:/root/.halo \
mdx/arm-holo:v1
```