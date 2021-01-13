---
title: He DNS 自动更新ip脚本
urlname: He DNS 自动更新ip脚本
typora-root-url: ../../source
date: 2021-01-11 16:19:39
tags: [ddns,动态域名]
index_img: https://gitee.com/iszheng/pico/raw/master/img/1610548833375-image-20210111162545352.png
---

### He DNS 自动更新ip脚本

随便一个目录下，创建sh文件

```shell
#!/bin/bash
#获取此时外网ip
current_ip=`curl -s members.3322.org/dyndns/getip`

#判断ip是否改变
#读取文件
#如果文件不存在，则创建文件
ip_file="ip_file"
if [ ! -f "$ip_file" ] ; then
        touch "$ip_file"
fi

last_ip=$(cat ./ip_file)

if [ "$current_ip" != "$last_ip" ]; then
        curl "https://需要解析的二级域名:动态域名的key@dyn.dns.he.net/nic/update?hostname=你的顶级域名&myip=$current_ip"
        echo "$current_ip" > "$ip_file"
fi
```

然后用crontab来执行

