---
title: nextjs 搭建个人站
date: 2019-12-14 14:15:18
tags:
  - react
  - ssr
  - nextjs
  - apollo-client
  - apolli-server
  - ant-design
category:
  - react
---

之前用react搭建了一套spa，但是感觉还差点啥，自己也从未体验过react、vue的服务端渲染，干脆着手搞一套react的ssr的个人站。

<!-- more -->

### 技术栈选择

#### 渲染框架

Next.js 是一个轻量级的 React 服务端渲染应用框架，使用简单，按照官网例子操作就能迅速构建以个react的ssr应用。

#### css预处理

以前为接触vue时使用过less，之后公司一直使用scss，在船新版本的个人站，我选择的stylus（写的代码量能够更少）

#### 接口服务

用习惯了RESTful风格的接口，自己也想尝试更新鲜的GraphQL风格的接口，就选择了apollo-serve、apollo-client搭建项目

#### 图片存储

一个个人站，总会存储图片，这里推荐使用七牛云，首先七牛云注册就会有10g的免费空间，作为一个流量小的网站，完全是足够了。

#### 数据库选择

选择了相对于前端来说语法相对js的mongodb，sql的select写起来太费劲了。

#### typescript

选择typescript，应该来说是很正常的，毕竟vue 3.0都拥抱ts了，自己也应该紧跟潮流，而且ts书写应用确实很香

总而言之，统而言之：项目的技术栈就确定为：nextjs graphql mongodb typescript stylus ant-design了，由于个人使用的是yarn管理依赖，使用npm的请对照着来，区别不大。

### 项目搭建

#### 依赖安装

新建项目文件夹，然后初始化项目

```bash
yarn init
```

安装nextjs相关依赖

```bash
yarn next react react-dom
```

将下面脚本添加到package.json中：

```json
{
  "scripts": {
    "dev": "next",
    "build": "next build",
    "start": "next start"
  }
}
```

....未完待续



