---
title: Linux下安装nginx
date: 2019-12-12 20:35:15
tags:
  - Linux瞎琢磨
category:
  - 这货不是Linux
---

服务器转发，我选择的是nginx,毕竟当时买腾讯云服务器买的乞丐版的，nginx对比起来内存消耗要低很多

1、安装nginx

```bash
yum install nginx -y
```

2、emm...就安装好了，然后启动nginx
```bash
nginx
```
3、此时访问域名或者ip就能看到nginx的欢迎页面了

4、设置nginx开机启动

```bash
systemctl enable nginx.service
```

