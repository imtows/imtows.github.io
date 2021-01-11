---
title: crontab 定时器
urlname: crontab_timer
date: 2021-01-11 01:20:20
tags: [crontab]
index_img: /images/8BDE8F8B-0B0C-4737-A959-1838AF57FB58.jpeg
typora-root-url: ../../source
---

### crontab 定时器的设定

#### 1，用命令调出编辑页面		

```shell
crontab -e
```

然后在最后添加下面这行

```shell
*/1 * * * * cd /home/ubuntu/sh/ddns && sh ./ddns.sh > log.log
```

关于命令，格式是 

*定时规则 命令*

定时规则网上一大堆，随便捞就是一大把，后面的命令，如果是shell的话，要指定日志输入或者输出指向null，否则，如果服务器没有配置邮箱的话，会报以下错误。

![错误提示](/images/image-20210111013052917.png)

