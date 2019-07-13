---
layout:     post
title:      "阿里云服务器实例购买及图形化界面配置"
subtitle:   " \" aliyun server configration\""
date:       2019-07-13 16:33:00
author:     "张凡"
header-img: "https://aerozf.oss-cn-beijing.aliyuncs.com/images/aliyunserver.jpg"
catalog: true
tags:
    - 服务器
    - 阿里云
---

# 1、阿里云服务器实例购买

1、进入阿里云官网
![](https://i.postimg.cc/d0htVJXJ/rn-Hp-ET5-png.png)

2、注册阿里云账号，或者使用淘宝账号或支付宝账号登录激活阿里云账号【如果已经注册的话直接登陆就可以了】
![](https://i.postimg.cc/5NmtP7LW/007i4-MEmgy1g23fh3gj2aj30dp0dct8m.jpg)

3、登陆后点击首页产品，找到热门产品>云服务器ECS，然后点击进入。
![](https://i.postimg.cc/bwCwPZm6/rn-Hrc-Uu-png.png)

4、点击立即购买
![](https://i.postimg.cc/q7WBt9Vy/2019041517123429.jpg)
5、选择一键式购买（新手要慢慢来，等用熟了在自定义购买，否则刚开始很容易出现很多问题），按需选择地域（这个可以随便选）、实例（也就是服务器配置）
![](https://i.postimg.cc/nhchN4Gj/20190415171356160.png)
6、选择系统镜像和系统版本（这里要注意了，要尽量选择自己熟悉的系统版本），建议选用Linux系统，Windows图形化界面太吃内存，这里我选用的是Ubuntu（Linux） 16.04 位系统。
![](https://i.postimg.cc/wM8Brnwg/20190415171729892.png)
7、网络和带宽选择默认的即可（带宽越大，价格越高），购买量即服务器购买时长根据自己的需求选择（刚开始可以选择买一个月试试手，熟悉了之后建议按年份买，这样实惠一些）
![](https://i.postimg.cc/hvLGRMYx/20190415172458767.png)
8、最后确认一下配置是否满足自己需求，确认没问题后付款就付款了，OK，服务器购买完成。
![](https://i.postimg.cc/HWXnMsLx/20190415172805356.jpg)
9、最后进入控制台配置一下登陆密码啥的，服务器就正式购买完成了。
![](https://i.postimg.cc/Hx7xBT46/20190415173049683.png)
10、登陆密码等设置好之后，找个putty工具远程ssh连接试一下，OK，到这里服务器就算购买完成了。
![](https://i.postimg.cc/TYxwJMyc/20190415173338120.jpg)

备注：阿里云服务器对在校大学生有优惠活动，如果目前还在校的话强烈建议通过大学生身份购买，能便宜不少（我买的那个一年的服务器才花了114块钱，如果正常购买的话需要至少1700+）

# 2、服务器图形界面配置（桌面配置）

上一小节讲了阿里云服务器购买的相关流程，但是对于新手，用Linux命令行来远程连接服务器可能用的不是那么习惯，甚至会出错，走很多弯路。所以我们可以安装图形化界面（我们熟悉的Windows系统就大量使用用户图形界面），以便于慢慢适应Linux系统的操作风格和远程部署服务器。

一、服务器配置


本文中使用阿里云服务器ECS，配置为单核CPU，2G内存。使用Ubuntu 16.04系统，搭配40G的云盘


二、安装ubuntu-desktop


1、通过putty或者Windows系统命令行远程ssh连接服务器
![](https://i.postimg.cc/TYxwJMyc/20190415173338120.jpg)
2、首先更新软件库
```
apt-get update
```

3、升级软件
```
apt-get upgrade
```

4、安装桌面（比较大，可能得下载好几分钟，请耐心等待）
```
sudo apt-get install ubuntu-desktop
```

5、等下载完成后重启服务器
![](https://i.postimg.cc/qvL1Q3kv/20190415180814894.png)
6、在阿里云网页端远程连接
![](https://i.postimg.cc/g02N72Jq/20190415181017641.png)

7、会发现只能以guest进行登录，但是无法使用root进行登录

所以。。。。。。

三、配置以root身份登录

1、通过putty或者Windows系统命令行远程ssh连接服务器，登陆后输入以下命令（操作之前建议学学nano的相关操作）
```
sudo nano /usr/share/lightdm/lightdm.conf.d/50-ubuntu.conf
```

2、修改成下面的语句，然后Ctrl X > Y 保存后退出
```
[Seat:*]
user-session=ubuntu
greeter-show-manual-login=true
allow-guest=false
```

3、由于登录后会有警告，因此按下面的修改可以去除警告
```
sudo nano /root/.profile
```

4、将最后一行修改为如下所示，Ctrl X > Y 保存后退出
```
tty -s && mesg n || true
```

5、最后在阿里云浏览器中重启服务器，重启完成后发现可以root 登陆桌面了
![](https://i.postimg.cc/MG3dJJfk/20190415182533940.png)
