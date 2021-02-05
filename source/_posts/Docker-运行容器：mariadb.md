---
title: Docker 运行容器：mariadb
urlname: Docker 运行容器：mariadb
date: 2021-01-16 21:25:41
tags: [docker,mysql,mariadb]
index_img:
---

### 需求背景

Mysql 没有官方的arm64版本docker镜像，树莓派上面要使用mysql，只能用Mariadb

### 运行脚本

```
docker run \
--name mariadb \
--restart=always \
-v /hardDisk/dockerData/mariadb/data/:/var/lib/mysql \
-v /hardDisk/dockerData/mariadb/conf:/etc/mysql/conf.d \
-e MYSQL_ROOT_PASSWORD=my-secret-pw \
-d \
mariadb
```

**第一个挂载，数据库文件**

```
-v /hardDisk/dockerData/mariadb/data/:/var/lib/mysql \
```

**第二个挂载，数据库配置**

```
-v /hardDisk/dockerData/mariadb/conf:/etc/mysql/conf.d \
```

**设置密码为 my-secret-pw** 

```
-e MYSQL_ROOT_PASSWORD=my-secret-pw \
```

