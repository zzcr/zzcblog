---
title: 利用hexo和码云pages搭建高速流畅的免费技术博客系列文章1--为啥用码云pages以及码云pages的简单应用。
date: 2017-04-16 10:05:06
tags: [blog]
categories: [博客搭建]
---
 这是一个系列文章，该系列文章将探讨如何一步步地搭建一个可高速浏览的免费技术博客,成品案例参考我的博客：[zzc的博客](http://ajaxzheng.oschina.io/)。
<!-- more -->
## 一.为啥使用码云pages而不使用gitHub pages
作为中国版的gitHub【全球最大的同性交友网站】，码云已经发展的足够强大了，gitHub提供的功能，码云都提供了而且还增加了免费建立私有仓库的功能。相信大家也经常发现gitHub会时不时的“大姨妈”【间歇性的被墙】,也许很多人会说：作为一个程序员不会翻墙你开发个卵子。好吧......但是你的博客是面向初，中，高级别程序员的技术博客，可以预想初级的或者是入门级的读者会占绝大部分，你能保证你的读者都会翻墙吗？而且你会发现即使你会翻墙，在访问码云pages和gitHub pages的访问速度也不是一个档次的，码云的访问速度差不多比gitHub快了接近1s【当然不同页面有一定的误差】。码云的使用方法几乎和gitHub的使用方法一模一样。综上所述，我决定用码云pages替代gitHub pages。
## 二.如何使用码云的pages功能
### 1. 在码云的[官网](https://git.oschina.net/)注册账户即可。
### 2. 和gitHub一样配置自己的公钥，具体如何配置可参考[码云的帮助文档](http://git.mydoc.io/?t=154712)，注：添加用户的ssh-key即可，项目的ssh-key暂时可以忽略。
### 3. 新建自己代码库，可以点击项目标签下的+号，也可直接点击右上角的加号。
![](http://omqvgxrwm.bkt.clouddn.com/1.png)
### 4. 给自己的项目添加一个名称和介绍，比如就叫blog，简介随便填什么都可以，也可不填，类别选择HTML，然后点击创建
![](http://omqvgxrwm.bkt.clouddn.com/2.png)
### 5. 创建完成之后，在本地新建一个与码云线上的仓库名称相同的项目，在index.html文件中加入h1标签并写入this is my blog，项目架构如下图所示：
![](http://omqvgxrwm.bkt.clouddn.com/3.png)

### 6. 初始化git【默认已经安装了git】，进入blog文件夹，点击右键，然后点击：Git Bash Here，然后输入下面的命令：
```
git init
git add - -all
git commit -m "this is my blog"
git remote add origin git@git.oschina.net:your-name/blog.git
git pull --rebase origin master
git push -u origin master

```
接下来我来逐行解释一下上面的命令代码：
* git init 初始化git版本库。
* git add - -all 添加所有文件到本地版本库,- -all代表所有文件【除了.gitignore文件里指名的文件】。
* git commit -m "this is my blog" 提交本地版本库,-m标识提交信息【后面双引号就是提交信息的具体内容】，表示为什么要提交本次修改内容。
* git remote add origin git@git.oschina.net:your-name/blog.git 连接远程版本库【就是链接码云上的线上仓库】，其中your-name表示你的码云用户名，不要直接复制哦！！！blog.git中的blog就是你刚才新建的线上版本库。也可直接复制你的码云线上的SSH链接。
![](http://omqvgxrwm.bkt.clouddn.com/4.png)
* git pull --rebase origin master 进行代码合并，很多人在连接远程版本库之后就直接git push -u origin master，然后控制台会报错：
```
$ git push -u origin master
To git.oschina.net:ajaxZheng/blog.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@git.oschina.net:ajaxZheng/blog.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

```
出现错误的主要原因是码云中的README.md文件不在本地代码目录中,可以通过如下命令进行代码合并【注：pull=fetch+merge】 git pull --rebase origin master，执行上面代码后可以看到本地代码库中多了README.md文件
* git push -u origin master 推送到远程版本库。推送成功后你在线上就能看到你的本地版本库在线上显示：
![](http://omqvgxrwm.bkt.clouddn.com/5.png)
### 7. 生成码云pages，和gitHup不同的是码云不用gh-pages分支即可生成静态页面，在master分支上一样可以生成静态页面，只需点击服务下面你的pages即可。
![](http://omqvgxrwm.bkt.clouddn.com/6.png)
### 8. 生成页面，点击开始部署然后就可以得到页面的url：
![](http://omqvgxrwm.bkt.clouddn.com/7.png)
点击连接就可以访问你的页面了
![](http://omqvgxrwm.bkt.clouddn.com/8.png)
是不是感觉很简单！！！这样你就拥有了自己的免费的静态网站了。
