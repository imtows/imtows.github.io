---
title: Docker 运行容器：adguardhome
urlname: Docker 运行容器：adguardhome
date: 2021-01-13 23:06:00
tags: [docker,adguard,广告]
index_img: https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-08-31-5d4405.png
---

Docker 运行容器：adguardhome

安装容器之前，先走两条命令

重点：见另一篇，ubuntu 释放 53 端口

sudo systemctl stop systemd-resolved

sudo systemctl disable systemd-resolved

不然53端口被占用，就跑不起容器了

```
docker run \
--name adguardhome \
-v /hardDisk/dockerData/adguard:/opt/adguardhome/work \
-v /hardDisk/dockerData/adguard:/opt/adguardhome/conf \
-p 53:53/tcp \
-p 53:53/udp \
-p 667:67/udp \
-p 668:68/tcp \
-p 668:68/udp \
-p 880:80/tcp \
-p 4443:443/tcp \
-p 8853:853/tcp \
-p 3000:3000/tcp \
-d \
adguard/adguardhome
```



安装完后，登陆

http://IP:3000/

![image-20210106221405327](https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-08-31-5d4405.png)



网页端口改成3000

![截屏2021-01-06 下午10.14.41](https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-08-46-4611a5.png)



配置：

![image-20210106222153655](https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-08-59-be42d6.png)

上游dns：最终解析url的dns

下面的方式选择并行





![image-20210106222252497](https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-09-10-c71f3b.png)

Bootstrap DNS 这里是解析上游DNS服务器用的，用运营商的dns就可以





添加规则

https://www.right.com.cn/forum/forum.php?mod=viewthread&tid=4030183 这个帖子里有，不行就google

<img src="https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-09-21-74053e.png" alt="截屏2021-01-06 下午10.28.24" style="zoom:50%;" />







重点，配置路由器，不然这个服务白搭了

![截屏2021-01-06 下午10.30.02](https://gitee.com/iszheng/pico/raw/master/img/2021-01-13-23-09-30-240a1f.png)



其他设备，修改dns地址到树莓派的ip就行了



重启路由器，测试是否生效