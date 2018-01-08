---
title: 本地博客同步到GitHub
tags: [Git,Github,npm,Hexo]
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
2）生成静态页面并部署
``` bash
 $ hexo g -d   #生成静态页面并部署
 
``` 
### 本地博客同步到GitHub
注：熟练掌握git命令
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
### 每次部署完之后需执行如下操作以达到同步的目的
``` bash
  git add .    #所有变化提交到暂存区
  git commit -m "本地博客同步到GitHub.md"   #提交文件
  git push origin branchname       #推送back分支（branchname名称命名为back）
 
```
### git命令
``` bash
 git config --global user.name [username]  配置用户名
 git config --global user.email [email]	  配置邮箱
 git init    初始化git仓库
 git status  检查文件是否有被修改
 git diff    查看文件修改的内容
 git commit  提交文件
 git log     显示从最近到最远的提交日志  --pretty=oneline  整理输出内容
 git reset --hard HEAD^  回退到上个版本     上上一个版本就是HEAD^^，当然往上100个版本写100个^比较容易数不过来，所以写成HEAD~100
 git reset --hard xxxxx 回退到指定版本
 git reflog  记录每一次命令
 git checkout -- file   把file文件在工作区的修改全部撤销    命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令
 git reset HEAD file    可以把暂存区的修改撤销掉（unstage），重新放回工作区
 git rm file   删除文件   要从版本库中删除该文件，那就用命令git rm删掉，并且git commit
 ssh-keygen -t rsa -C "875727617@qq.com" 创建SSH Key
 git push origin master  把本地master分支的最新修改推送至GitHub
 git checkout -b dev     git checkout命令加上-b参数表示创建并切换   ---相当于git branch dev   git checkout dev
 git merge dev   合并dev分支到当前分支
 git branch -d dev  删除dev分支  -D 大写D是强行删除没有合并的分支
 git branch 查看分支
 git branch <name>  创建分支
 git log --graph --pretty=oneline --abbrev-commit  查看分支的合并情况
 git stash      把当前的工作区隐藏
 git stash list 查看隐藏的工作区
 git stash apply 恢复之前隐藏工作区
 git stash drop  删除之前隐藏的工作区
 git stash pop   恢复并删除之前隐藏的工作区
 git remote      查看远程库的信息    -v 显示更详细的信息
 git push origin master   推送master分支
 git push origin <name>   推送标签到远程  --tags 一次性推送全部尚未推送到远程的本地标签
 git tag <name>  用于新建一个标签，默认为HEAD，也可以指定一个commit id；
 git tag -a <tagname> -m "blablabla..."可以指定标签信息；
 git tag -s <tagname> -m "blablabla..."可以用PGP签名标签；
 git tag 可以查看所有标签
 git show tag <name>  查看标签内容
 git tag -d <name>    删除标签
 git push origin :refs/tags/v0.9  删除远程的分支，先本地删除分支
 gitignore   忽略特殊文件,然后把要忽略的文件名填进去
 git config --global alias.co checkout  配置别名 
 git pull origin back 取回远程主机某个分支的更新
```
### 删除并添加新的md文件操作
``` bash
 在本地和github删除md文件/git rm 要删除的文件名称
 git pull origin back   #取回远程主机某个分支的更新
 git add .    #所有变化提交到暂存区
 git commit -m "新增md文件名称.md"    #提交文件
 git push origin branchname     #推送back分支（branchname名称命名为back）
 
```