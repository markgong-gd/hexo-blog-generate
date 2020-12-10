---
title: hexo、github搭建个人博客
cover: 'https://raw.githubusercontent.com/markgong-gd/images/main/images/blog/wallhaven/wallhaven-96688w.jpg'
coverWidth: 1200
coverHeight: 675
layout: post
categories:
  - 建站笔记
tags:
  - 博客
date: 2020-12-10 09:59:46
---

基于hexo、github搭建个人博客随手笔记

<!--more-->

## 为什么要写这篇文章

自己第一次搭建在网上找了一些文章，但是感觉文章没啥区别，按照步骤来发现好多坑。希望这篇文章可以不上一些坑。

## 为什么选择Hexo

1. 发现[Vue](https://cn.vuejs.org/index.html)官网也是用了Hexo，跟随大佬的步伐。
2. 个人之前有参与过基于Gatsby + Docz + Theme UI开发的项目---[腾讯直播](https://ilive.qq.com/)，写法结构上有点类似。
3. 社区有一些不错的主题可以使用，比较便捷s。

## 搭建前准备

1. git
2. node.js

这里这两个环境相信大家应该都配置好了，如果还没配置可以百度下。

## 正式搭建

可以进入官网仔细了解：[Hexo](https://hexo.io/zh-cn/)

```sh
npm install hexo-cli -g
```

安装完成之后，创建一个 ***空文件夹*** 在这个文件下执行下面命令

```sh
hexo init
```

执行完成后，你会发现文件夹下生成一些文件，文件具体意义可以参考官网文档了解。**写博客前先了解下是很有必要的**

分别执行以下命令，打开 localhost:4000, 就可以跑起来了。

```sh
hexo generate
hexo server
```

## 将博客部署到自己gitbuh.io上

以我自己的地址为例：https://github.com/markgong-gd/markgong-gd.github.io.git

在刚刚生成的文件里找到 ***_config.yml*** 文件，修改以下配置

```yml
# URL
## If your site is put in a subdirectory, set url as 'http://example.com/child' and root as '/child/'
url: https://markgong-gd.github.io/

deploy:
  type: git
  repo: https://github.com/markgong-gd/markgong-gd.github.io.git
  branch: master
```

- 安装部署工具

```sh
npm install hexo-deployer-git --save
```

执行部署命令

hexo clean： 清楚缓存
```sh
hexo clean
hexo deploy
```

现在可以在你的 {github username}.github.io 看到你的页面了

## 主题使用

[Hexo Theme](https://hexo.io/themes/)

找到你需要的主题进入 ***themes*** 文件夹，***在themes下***克隆 `git clone https://github.com/<username>/<reponame>`

返回到根目录执行以下命令

```sh
hexo generate
hexo server
```

打开 localhost:4000 验证是成功，执行部署命令发布

最后有问题，可以评论，看到会回复！文笔不好，感谢大家支持！

