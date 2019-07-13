---
layout:     post
title:      "frp服务器和客户端配置（内网穿透）"
subtitle:   " \" frp server and client configuration\""
date:       2019-07-13 17:01:00
author:     "张凡"
header-img: "https://aerozf.oss-cn-beijing.aliyuncs.com/images/frp_network.jpg"
catalog: true
tags:
    - 服务器
    - frp
---

如果没有公网ip，但又想随时随地都能连接到没有公网ip的机器（例如树莓派、办公室电脑等），我们可以使用 frp 来实现。

## 1、准备条件

需要一个有公网ip的服务器（例如阿里云服务器）

## 2、服务端配置 - frps

frp 的服务器端，一般名为 frps，配置文件是 frps.ini。可以在 frp 官方页面 获取到最新版本的下载链接（此处以 frp_0.17.0_linux_amd64 为例）。接着使用 ssh 登录 vps 端操作，命令行如下：
```
wget https://github.com/fatedier/frp/releases/download/v0.26.0/frp_0.26.0_linux_amd64.tar.gz
tar -zxvf frp_0.26.0_linux_amd64.tar.gz
cd frp_0.26.0_linux_amd64
nano frps.ini
```

配置文件内容如下：
```
[common]
bind_port = 7000
vhost_http_port = 80
dashboard_port = dashboard_port_number
dashboard_user = dashboard_user_name
dashboard_pwd = dashboard_pwd_value
privilege_token = privilege_token_value
```
ctrl+o 保存，之后 回车 确认，然后 ctrl+x 退出。
参数说明

- bind_port：绑定的端口，需要与客户端中 server_port 参数保持一致
- vhost_http_port：虚拟主机运行在本机的端口，如果 vps 有服务占用了端口，应当更换
- dashboard_port：frp 后台服务页面的端口，如果设置 8000，便可通过 http://yourip:8000 来访问 frps 的后台页面
- dashboard_user：frp 后台服务页面的管理员用户名
- dashboard_pwd：frp 后台服务页面的管理员密码
- privilege_token：自定义值，必须与客户端中的 privilege_token 保持一致

配置完成之后，便可以通过如下命令启动 frps：
```
./frps -c ./frps.ini
```
为了让服务器一直运行 frp 服务，可以把frp服务加入supvisor中，在/etc/supervisor/config.d的文件夹中新建一个名为frp.config的文件，在里面写入如下命令：
```
[program:frp]
command = /root/frp_0.26.0_linux_amd64/frps -c /root/frp_0.26.0_linux_amd64/frps.ini
autostart=True
```
然后在系统命令行中输入如下命令frp就会开机自动运行了。
```
supervisorctl reload
supervisorctl start frp
```
## 3、客户端配置 - frpc

frp 的客户端，一般名为 frpc，配置文件是 frpc.ini。同样可以在 frp 官方页面 获取到最新版本的下载链接（此处以 frp_0.17.0_linux_arm 为例）。接着使用 ssh 登录 vps 端操作，命令行如下：
```
wget https://github.com/fatedier/frp/releases/download/v0.26.0/frp_0.26.0_linux_arm.tar.gz
tar -zxvf frp_0.26.0_linux_arm.tar.gz
cd frp_0.26.0_linux_arm
nano frpc.ini
```
配置文件内容如下：
```
[common]
server_addr = your_server_ip
server_port = 7000
privilege_token = privilege_token_value
login_fail_exit = false

[ssh]
type = tcp
local_ip = 127.0.0.1
local_port = 22

remote_port = remote_port_number
```
ctrl+o 保存，之后 回车 确认，然后 ctrl+x 退出。
参数说明

- server_addr：服务器端的 ip
- server_port：服务器端的端口，即 bind_port
- privilege_token：同服务器端的 privilege_token 保持一致
- login_fail_exit：失败时自动重连
- remote_port：远程端口，即 ssh 连接树莓派时的端口

配置完成之后，便可以通过如下命令启动 frps：
```
./frpc -c ./frpc.ini
```
同时为了让客户端一直运行 frp 服务，可以把frp服务加入supvisor中，在/etc/supervisor/config.d的文件夹中新建一个名为frp.config的文件，在里面写入如下命令：
```
[program:frp]
command = /root/frp_0.26.0_linux_arm/frpc -c /root/frp_0.26.0_linux_arm/frpc.ini
autostart=True
```
然后在系统命令行中输入如下命令frp就会开机自动运行了。
```
supervisorctl reload
supervisorctl start frp
```

---------------------
本内容参考自：
- 作者：涂涂涂w
- 链接：https://www.jianshu.com/p/a921e85280ed
