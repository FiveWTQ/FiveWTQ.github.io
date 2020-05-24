---
title: hexo常用安装插件
author: Tong Qing Wu
top: true
cover: true
toc: true
mathjax: false
summary: hexo必装的一些插件
date: 2020-05-24 15:39:47
img:
coverImg:
password:
categories:
	- hexo
tags:	
	- hexo
---

## 代码突出显示
Hexo主题使用Hexo的插件hexo-prism-plugin而不是其自己的主题来显示代码突出显示。安装命令如下：
```
npm i -S hexo-prism-plugin
```
然后，在Hexo根文件夹的文件中修改highlight.enableto 的值，并添加插件的配置，如下所示：false_config.ymlprism
```
highlight:
  enable: false

prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'tomorrow'
  line_number: false    # default false
  custom_css:
```
## 搜索功能
该主题使用Hexo插件hexo-generator-search搜索内容，安装命令如下：
```
npm install hexo-generator-search --save
```
_config.yml在Hexo根文件夹中添加文件配置，如下所示：
```
search:
  path: search.xml
  field: post
```
## 将中文链接翻译成拼音
如果您的体育馆标题是中文，则Hexo的Defualt永久链接将包括中文。但这不利于SEO，gitment注释也不支持中文链接。生成帖子时，我们可以使用Hexo插件的hexo-permalink-pinyin来生成中文拼音的永久链接。
安装命令如下：
```
npm i hexo-permalink-pinyin --save
```

在_config.ymlHexo文件中添加以下配置：
```
permalink_pinyin:
  enable: true
  separator: '-' # default: '-'
```
## 发布字数统计插件
如果要在帖子详细信息页面上显示帖子数和阅读时间信息，则可以安装hexo-wordcount插件。

安装命令如下：
```
npm i --save hexo-wordcount
```
然后只需激活主题_config.yml文件中的以下配置项
```
postInfo:
  date: true
  update: false
  wordCount: false # set true.
  totalCount: false # set true.
  min2read: false # set true.
  readCount: false # set true.
```
## 添加RSS feed支持
该主题使用Hexo插件hexo-generator-feed支持RSSfeed，并且Installation命令如下：
```
npm install hexo-generator-feed --save
```
_config.yml在Hexo根文件夹中添加文件配置，如下所示：
```
feed:
  type: atom
  path: atom.xml
  limit: 20
  hub:
  content:
  content_limit: 140
  content_limit_delim: ' '
  order_by: -date
```
执行hexo clean && hexo g以重新生成博客文件，然后您可以在atom.xml文件public夹中看到该文件，表明您已成功安装。

## 一般就用的
```
npm install
npm install hexo-deployer-git --save  // 文章部署到 git 的模块
（下面为选择安装）
npm install hexo-generator-feed --save  // 建立 RSS 订阅
npm install hexo-generator-sitemap --save // 建立站点地图
```