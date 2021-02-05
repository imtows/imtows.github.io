---
title: Docker 运行容器：nextcloud
urlname: Docker 运行容器：nextcloud
date: 2021-01-16 21:49:31
tags:
index_img:
---

#### 运行脚本

##### 1拉取镜像

```
docker pull nextcloud
```

尝试过fpm搭建，搞了好久，放弃，直接用默认apache吧

##### 2运行容器

```
docker run \
--name nextcloud \
-d \
-p 8080:80 \
-v /hardDisk/dockerData/nextcloud/data:/var/www/html \
nextcloud
```

**挂载**

```
-v /hardDisk/dockerData/nextcloud:/var/www/html \
```

将整个目录挂载出来，省事

##### 3 配置

![截屏2021-01-17 下午8.07.27](https://gitee.com/iszheng/pico/raw/master/img/2021-01-17-20-09-05-67f441.png)

第一次配置，时间比较久，耐心等待。

到此安装完成，后续配置下次一定

