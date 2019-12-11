---
title: hexo + github pages构建博客
tags:
  - 菜鸡互啄
---

来来回回试过好几种方式来构建自己的博客了，断断续续的使用react写了spa博客、用apollo-server + mongodb写了后台接口，之后又用next + ts重构博客中，然后顺手又试验了下hexo，果然还是使用hexo + githubPages的方式开发个人博客最简单。

<!-- more -->

### 关于hexo

安装
```bash
$ npm install -g hexo-cli
```
初始化项目
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
注意不要在这个文件夹下面试用 Git 创建仓库，因为后面安装的主题内可能会带有 git 仓库，这样会导致包管理的混乱。

### github pages

新建一个项目

### hexo和github关联

在_config.yml中找到

```
deploy:
  type: git
  repo: https://github.com/justpeth/blog.git
  branch: master
```
repo填写github的地址，branch填写分支

此时，本地的hexo项目还无法部署到github中去，需要一个额外依赖：

```bash
$ npm install hexo-deployer-git --save
```

现在可以使用hexo命令构建项目
```bash
$ npm run build
```
然后部署到github上
```bash
$ npm run deploy
```
项目成功的部署到了github上了

### githubPages设置

进入github项目，进入setting，找到对应GitHub Pages设置的地方，

![githubPagesSetting](http://pic.justpeth.com/githubPages-setting.png)

### hexo 设置CNAME

一般情况下，如果githubpages配置了自己的域名，hexo每次部署上去都会重置这个域名，这个时候需要你再hexo项目中新建一个CNAME的文件，文件中输入自己配置的域名就行。