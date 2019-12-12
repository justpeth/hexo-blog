---
title: pm2安装
date: 2019-12-12 20:38:10
tags:
  - Linux瞎琢磨
category:
  - 这货不是Linux
---

pm2是一个进程管理工具,可以用它来管理你的node进程，并查看node进程的状态，当然也支持性能监控，进程守护，负载均衡等功能（编不下去了...）

<!-- more -->

1、安装pm2需要先安装node

2、全局安装pm2

```bash
npm install -g pm2
```
安装完成后如下提示
```bash
/node-v10.16.2/node/bin/pm2 -> /node-v10.16.2/node/lib/node_modules/pm2/bin/pm2
/node-v10.16.2/node/bin/pm2-dev -> /node-v10.16.2/node/lib/node_modules/pm2/bin/pm2-dev
/node-v10.16.2/node/bin/pm2-docker -> /node-v10.16.2/node/lib/node_modules/pm2/bin/pm2-docker
/node-v10.16.2/node/bin/pm2-runtime -> /node-v10.16.2/node/lib/node_modules/pm2/bin/pm2-runtime
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@2.1.2 (node_modules/pm2/node_modules/fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@2.1.2: wanted {"os":"darwin","arch":"any"} (current: {"os":"linux","arch":"x64"})
+ pm2@4.1.2
added 204 packages from 199 contributors in 69.493s
```

安装后，查看pm2版本

```bash
pm2 -v
```

结果提示

```bash
-bash: pm2: command not found
```

需要对pm2添加软链

```bash
ln -s /node-v10.16.2/node/bin/pm2 /usr/local/bin/pm2
```

结果失败了，啊哈哈哈...

```bash
[root@VM_0_15_centos ~]# ln -s /node-v10.16.2/node/bin/pm2 /usr/local/bin/pm2
ln: failed to create symbolic link ‘/usr/local/bin/pm2’: File exists
```

进行操作

```bash
mv /usr/local/bin/pm2 /tmp/
```

再重新设置软链

```bash
ln -s /node-v10.16.2/node/bin/pm2 /usr/local/bin/pm2
```

终于没有报错提示了，可以放心全局使用pm2了

```bash
[root@VM_0_15_centos ~]# pm2 -v
[PM2] Spawning PM2 daemon with pm2_home=/root/.pm2
[PM2] PM2 Successfully daemonized
4.1.2
```
