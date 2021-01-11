---
title: PicGo+Gitee搭建在线图床
urlname: PicGo+Gitee搭建在线图床
typora-root-url: ../../source
date: 2021-01-11 21:35:12
tags: [PicGo,gitee,图床,在线]
index_img: /images/image-20210112012538693.png
---

### PicGo+Gitee搭建在线图床

#### 1需求背景

​		因为博客是搭在github上的，github本身速度就慢，如果文章图片太多的话，那速度估计泡杯茶回来才能完全加载完。所以需要一个在线图床在做图片的载体，提高博客的响应速度。用这个笔记记录整个搭建过程。

#### PicGo部分

##### 1，下载PicGo

```url
https://github.com/Molunerfinn/PicGo/releases
```

![releases页面](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.42.54.png)

第一次使用，还是选择正式版比较稳妥，往下拉，找到最新的正式版来用。

![截屏2021-01-11 下午9.45.13](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.45.13.png)

这里下载2.2.2稳定版。（PicGo-2.2.2.dmg）

这里吐槽一下，软件打开，默认是没有任何界面，图标躲在上面状态栏里面，右击弹出菜单

![截屏2021-01-11 下午9.49.24](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.49.24.png)

![截屏2021-01-11 下午9.50.58](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.50.58.png)



##### 2，下载Gitee插件

![截屏2021-01-11 下午9.55.03](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.55.03.png)

选择gitee-uploader这个插件下载安装。

然后配置插件

![截屏2021-01-11 下午9.58.53](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%889.58.53.png)

repo：仓库名称；

branch：pages的分值；

token：

path:

customPath:

customUrl:

这些配置等下面gitee弄好再回来设置

##### 3，下载picgo-plugin-compress和imagemin插件

不知道是什么原因，之前在插件设置里面无法安装picgo-plugin-compress插件，去picgo-plugin-compress的 [github](https://github.com/JuZiSang/picgo-plugin-compress) 页面找，发现了[离线安装](https://picgo.github.io/PicGo-Core-Doc/zh/dev-guide/deploy.html#gui%E6%8F%92%E4%BB%B6)的方法。

<img src="/images/%E6%88%AA%E5%B1%8F2021-01-12%20%E4%B8%8A%E5%8D%881.13.55.png" alt="截屏2021-01-12 上午1.13.55" style="zoom:50%;" alt="right" />



###### 3.1进入PicGo的目录

```
/Users/用户名/Library/Application Support/picgo
```

###### 3.2 安装插件

```
npm install 插件名
```

这里要安装的是picgo-plugin-compress、imagemin

```
npm install picgo-plugin-compress
npm install imagemin
```

###### 3.3启用插件并重启PicGo

![image-20210112011950932](/images/image-20210112011950932.png)







#### Gitee部分

##### 1创建pages仓库

![截屏2021-01-11 下午10.02.49](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%8810.02.49.png)

填好3个红框的信息，然后创建仓库

##### 2创建私人token

token在个人设置里面获取

![截屏2021-01-11 下午10.07.52](/images/%E6%88%AA%E5%B1%8F2021-01-11%20%E4%B8%8B%E5%8D%8810.07.52.png)

勾选这个就可以，然后填一下描述，就可以创建了。注意！toekn只显示一次，要保存好。

然后回到上面的插件设置，填入相应的信息。

repo:Gitee用户名/仓库名称

token：刚刚创建的token

其他留空即可




