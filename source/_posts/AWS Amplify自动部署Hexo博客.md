---
title: AWS Amplify自动部署Hexo博客
date: 2022-11-19 20:50:39
tags: ["AWS", "Hexo", "ICARUS"]
categories: 博客
---

今天决定重新开始写博客了，平时都是在 Obsidian 上写作，所以选择 Hexo 作为博客框架，Hexo 使用  [Markdown](http://daringfireball.net/projects/markdown/)（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。

## 安装 Hexo

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

- [Node.js](http://nodejs.org/) v16.16.0
- [Git](http://git-scm.com/) git version 2.18.0

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```bash
$ npm install -g hexo-cli
```

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。

```bash
$ hexo init <folder>
$ cd <folder>
$ npm install
```

本地启动

```shell
# 生成静态网站
$ hexo g
# 启动服务器
$ hexo s
```

## 选择主题

在 Github 官网搜索 `hexo-theme`，选择 `All GitHub`，或者直接进入搜索页：[search?q=hexo-theme](https://github.com/search?q=hexo-theme) 找到心仪的主题.

我选的是 [hexo-theme-icarus](https://github.com/ppoffice/hexo-theme-icarus)，执行一下命令修改主题。

```bash
$ npm install hexo-theme-icarus
$ hexo config theme icarus
```

重启启动查看主题是否更新成功

```bash
$ hexo clean && hexo g && hexo s
```

创建一篇博客

```bash
$ hexo new <title>
```

## 提交 Github 仓库

```bash
$ git add .
$ git commit -m "first commit"
$ git branch -M main
$ git remote add origin <git_repository_url>
$ git push -u origin main
```

## 部署到 AWS Amplify

很简单 Github 授权，选择仓库，Build 即可
![](/images/CleanShot 2022-11-19 at 21.44.15.png)

## 连接到自己的域名

在 AWS Amplify 的 Domain management 中，选择”Add domain”并进行配置，接下来 Amplify 会验证你对域名的所有权，按照提示在你的域名管理站点中添加相应的 CNAME 记录。
![](/images/CleanShot 2022-11-19 at 21.46.24 1.png)

大功告成!!!
