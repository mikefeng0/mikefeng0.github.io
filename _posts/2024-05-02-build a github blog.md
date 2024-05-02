---
title: 如何搭建Github Blog
date: 2024-05-02 21:30:00 +0800
categories: [Blogging, github]
tags: [Tutorial]     # TAG names should always be lowercase
author: <author_mike>                     # for single entry
---

## 简介


[GiHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages)提供了免费搭建Blog的功能，为了页面美观以及网站的功能性，可以使用Jekyll构建网页，这里选用[chirpy](https://github.com/cotes2020/jekyll-theme-chirpy)主题。

## 步骤

主要参考[chripy的官方指南](https://chirpy.cotes.page/posts/getting-started/)。

### 安装Jekyll依赖

参照[Jekyll](https://jekyllrb.com/docs/installation/)官网操作就好，建议按照官网的流程走一遍完整的安装流程，否则可能出现虽然主页介绍的“Requirements”都满足要求，本地编译仍然会发生异常。

### 导入Chirpy Starter模板

有两种使用chripy主题的方式，为了方便，参照的直接导入Starter模板的方式。

1. 进入[chirpy-starter](https://github.com/cotes2020/chirpy-starter)项目主页，点击“Use this template”
2. 仓库名注意要填写为“账号名称.github.io”

### 配置
* 克隆github.io项目到本地，进行修改
* 注意首次要进入项目根目录执行命令：`bundle`
* 主要修改*_config.yml*文件中的相关项：
  * url
  * avatar

### 构建 & 预览

* 本地预览：`bundle exec jekyll s`
* 重新构建：`bundle exec jekyll build`

### 写文章

要先记录`author`信息，在'_data/authors.yml'（如果没有这个文件，创建它）中填入：
```
<author_id>:
  name: <full name>
  twitter: <twitter_of_author>
  url: <homepage_of_author>
```

然后开始写作：
* 文章在`_posts`文件夹中存放
* 需要按照`YYYY-MM-DD-TITLE.md`格式命名
* 文章开头需要填入：
    ```
    ---
    title: TITLE
    date: YYYY-MM-DD HH:MM:SS +/-TTTT
    categories: [TOP_CATEGORIE, SUB_CATEGORIE]
    tags: [TAG]     # TAG names should always be lowercase
    author: <author_id>     
    ---
    ```
* 图片文件可以存入`assets\img`中

### 部署

使用Github Actios部署：

* 进入github.io仓库的设置中，左侧栏点击“Pages”，右侧的“Build and deployment”下的“source”选择为“Github actions”
* push本地提交到github将会自动触发*Actions workflow*







