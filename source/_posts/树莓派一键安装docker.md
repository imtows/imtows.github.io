---
title: 树莓派一键安装docker
date: 2021-01-10 22:17:27
tags:
urlname: raspberry_install_docker
typora-root-url: ../../source
index_img: https://gitee.com/iszheng/pico/raw/master/img/1610548723724-8D2C13D5-7E03-4A42-B382-56DE0390296A.png
---

## 树莓派一键安装docker

### 1，下载一键安装的脚本

```
curl -fsSL https://get.docker.com -o get-docker.sh
```

### 2，运行脚本

```
sh get-docker.sh
```

### 3，等待脚本

4，不是root用户执行脚本，安装后出现如下图所示提醒

![image-20210113223807561](https://gitee.com/iszheng/pico/raw/master/img/1610548687618-image-20210113223807561.png)

只要依次运行如下脚本即可

```
sudo groupadd docker     #添加docker用户组
sudo gpasswd -a $USER docker     #将登陆用户加入到docker用户组中
newgrp docker     #更新用户组
```



