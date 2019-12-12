---
title: Linux下安装mongodb
date: 2019-12-12 20:26:25
tags:
  - Linux瞎琢磨
category:
  - 这货不是Linux
---

以前大学时学过sql，但是基本上忘得差不多了，而且写sql查询麻烦，感觉没有mongodb爽，接口服务就使用的mongodb，js语法的查询用着多好...

<!-- more -->

1、下载mongodb（下载的时候去官网找地址）

```bash
curl -O https://fastdl.mongodb.org/linux/mongodb-linux-x86_64-4.0.11.tgz
```

2、解压mongodb安装包

```bash
tar -zxvf mongodb-4.0.11.tgz
```

3、可以选择修改文件夹名字，方便自己记忆

```bash
mv mongodb-linux-x86_64-4.0.11 mongodb-4.0.11
```

4、新建数据库路径与日志文件存放路径

```bash
mkdir data
cd data
mkdir db
mkdir logs
```
5、设置开机启动

```bash
echo "/mongodb/mongodb-4.0.11/bin/mongod --dbpath=/mongodb/mongodb-4.0.11/data –logpath=/mongodb/mongodb-4.0.11/logs –logappend --bind_ip=0.0.0.0 --auth –port=27017" >> /etc/rc.local
```

6、设置账户权限

```bash
mongo
use admin
db.createUser({user: xxx, pwd: xxx, roles: [role: xxx, db: xxx]})
```

7、开启权限认证

如果是命令模式启动的话，就在原来的启动参数上，在加上 --auth 即可

```bash
mongod --auth --dbpath "D:\Program Files\MongoDB\Server\4.0\data"
```
如果是windows service方式运行的话，打开 mongo配置文件mongod.cfg, 在security项下，将authorization设置为enabled, 默认是disabled

```bash
security:
  authorization: enabled
```
然后重启service就可以了

