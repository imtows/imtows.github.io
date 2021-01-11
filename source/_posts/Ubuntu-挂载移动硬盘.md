---
title: Ubuntu 挂载移动硬盘
urlname: Ubuntu 挂载移动硬盘
typora-root-url: ../../source
date: 2021-01-11 17:40:43
tags: [ubuntu]
index_img:
---

### Ubuntu 挂载移动硬盘

#### 1.插入新硬盘，启动Linux服务器，

使用fdisk -l 查看硬盘　　

fdisk -l

![image-20210111174242281](/images/image-20210111174242281.png)

根据硬盘大小判断是哪个硬盘，记住名称 /dev/sda



#### 2.格式化硬盘　　

mkfs -t ext4 /dev/sda



#### 3.挂载硬盘 　

mount 硬盘地址 要挂载的地址　　

mount /dev/sda /hardDisk

(  /hardDisk  系统上要有这个目录，没有的话要创建)



#### 4.实现系统重启后自动挂载该分区　　

vi /etc/fstab　　

在最后一行添加　　

/dev/sda /hardDisk ext4 defaults 1 2

前面 /dev/sda 为硬盘的位置，/hardDisk 为挂载点 后面的意思不懂，能用就行



![image-20210111174319716](/images/image-20210111174319716.png)