---
title: docker 修改镜像源
urlname: docker 修改镜像源
date: 2021-01-13 23:12:19
tags: [docker]
index_img:
---

docker 修改镜像源

```
cd /etc/docker

vi daemon.json
```

粘贴

```
{
  "registry-mirrors": ["https://rpq4iyui.mirror.aliyuncs.com"]
}
```

重启docker 

结束