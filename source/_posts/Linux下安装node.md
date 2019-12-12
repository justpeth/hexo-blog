---
title: Linux下安装node
date: 2019-12-12 20:21:49
tags:
  - Linux瞎琢磨
category:
  - 这货不是Linux
---

之前自己也写了一套博客，前端是react的spa，后台是采用的node服务，涉及到服务，就需要服务器环境配置，这里说下菜鸟是怎么一步一步搭建服务器环境的

<!-- more -->

1、在服务器上新件文件夹`node-v10.16.2`

2、在个人电脑上下载了最新的Linux环境下的安装包，然后通过FileZilla上传到服务器（node-v10.16.2文件夹下），然后进入node-v10.16.2文件夹解压安装：

```bash
cd /node-v10.16.2
xz -d node-v10.16.2-linux-x64.tar.xz
tar -xvf node-v10.16.2-linux-x64.tar
```

3、更改文件夹名字

```bash
mv node-v10.16.2-linux-x64 node
```

4、配置软链，可以全局使用npm、node、npx命令

```
ln -s /node-v10.16.2/node/bin/node /usr/local/bin/node
ln -s /node-v10.16.2/node/bin/npm /usr/local/bin/npm
ln -s /node-v10.16.2/node/bin/npx /usr/local/bin/npx
```