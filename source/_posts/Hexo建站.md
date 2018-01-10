---
title: Hexo建站
tags: [Node.js,Git,Hexo]
---


## hexo部署到Github 

### 安装Node.js
下载Node.js
参考地址：[安装Node.js](http://www.runoob.com/nodejs/nodejs-install-setup.html)

### 安装Git
下载地址：[安装git](https://git-scm.com/download/)

### 安装Hex
``` bash
 $ cd d:/hexo
 $ npm install hexo-cli -g
 $ hexo init blog
 $ cd blog
 $ npm install
 $ hexo g #或者hexo generate
 $ hexo s #或者hexo server,可以在http://localhost:4000/查看
```
![hexo创建图片](/images/hexo-init.png)
解析：
 . node_modules：是依赖包
 . public：存放的是生成的页面
 . scaffolds：命令生成文章等的模板
 . source：用命令创建的各种文章
 . themes：主题
 . _config.yml：整个博客的配置
 . db.json：source解析所得到的
 . package.json：项目所需模块项目的配置信息

hexo命令解析：
  1.hexo g：生成静态文件，会在当前目录下生成一个新的public文件夹。
  2.hexo s：启动本地web服务，用于博客的预览。
  3.hexo d：部署博客到远端（比如github、heroku等平台）。
### 常用命令
 ``` bash
 $ hexo new "postName"  #新建文章
 $ hexo new page "pageName"  #新建页面
 $ hexo n == hexo new
 $ hexo g == hexo generate
 $ hexo s == hexo server
 $ hexo d == hexo deploy
 $ hexo d -g  #生成部署
 $ hexo s -g  #生成预览
 
```
打开(http://localhost:4000/) 可以看到hexo内部的blog

![blog图片](/images/blog.png)
## Hexo主题设置

主题名称为test为例

### 安装主题
``` bash
 $ hexo clean
 $ git clone https://github.com/litten/hexo-theme-test.git themes/test
 
```
### 启用主题

修改Hexo目录下的_config.yml配置文件中的theme属性，将其设置为test。

### 更新主题

``` bash
 $ cd themes/test
 $ git pull
 $ hexo g  #生成静态文件
 $ git pull  #启动本地web服务器
```
### 创建主题(test)

``` bash
 $ cd f： #创建地址在f盘
 $ hexo init test  #新建test主题
 $ cd test   #进入test文件夹
 $ ls       #查询文件夹下的内容
 $ npm i/install   #进入项目，下载依赖
 $ hexo g    #生成静态文本
 $ hexo s     #启动本地web服务器

```





