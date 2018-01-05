---
title: 本地博客同步到GitHub
---


## hexo部署到Github 

### 使用hexo deploy部署
注：需要提前安装一个扩展
``` bash
 $ npm install hexo-deployer-git --save
```
 ![“git命令”](/images/deployer.png)
1）修改_config.xml的配置如下：

``` bash
 deploy:
  type:git
  repo:git@github.com:githunname/githubname.github.io.git
  branch:master
 
```
 ![“配置修改”](/images/deploy.png)
2）
``` bash
 $ hexo g -d   #生成静态页面并部署
 
```
### 本地博客同步到GitHub
在博客根目录下执行如下操作：
``` bash
  git init         #创建git仓库
  git remote add origin git@github.com:githubname/githubname.github.io.git   #添加远程仓库（githubname是自己的用户名）
  git checkout -b branchname   #新建branch分支（branchname为自己定义的分支名称）
  git add .    #所有变化提交到暂存区
  git commit -m "同步更改后的文件"   #提交文件
  git push origin branchname       #推送back分支（branchname名称命名为back）
 
```
 ![“本地博客成功部署到GitHub上”](/images/success.png)
## hexo部署到Github之后注意事项 
 每次部署完之后需执行如下操作以达到同步的目的
``` bash
  git add .    #所有变化提交到暂存区
  git commit -m "本地博客同步到GitHub.md"   #提交文件
  git push origin branchname       #推送back分支（branchname名称命名为back）
 
```