---
title: 树莓派一键安装docker
date: 2021-01-10 22:17:27
tags:
urlname: raspberry_install_docker
typora-root-url: ../../source
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

![](/images/image-20210110222015223.png)

只要依次运行如下脚本即可

```
sudo groupadd docker     #添加docker用户组
sudo gpasswd -a $USER docker     #将登陆用户加入到docker用户组中
newgrp docker     #更新用户组
```



