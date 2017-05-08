---
title: 利用hexo和码云pages搭建高速流畅的免费技术博客系列文章2--环境搭建和hexo的价绍与使用
date: 2017-04-16 15:49:44
tags: [blog]
categories: [博客搭建]
---
这是一个系列文章，该系列文章将探讨如何一步步地搭建一个可高速浏览的免费技术博客,成品案例参考我的博客：[zzc的博客](http://ajaxzheng.oschina.io/)。
<!-- more -->
作为一个有思想前端开发😭，一直以来我都想拥有自己的技术博客，因为刚入行不久决定自己在阿里云上买了个很便宜的服务器然后自己搭一套php集成开发环境，并在上面部署自己的博客系统，但是由于能力精力有限并且代码很难管理，最终这个计划不得已终止了。。。之后慢慢接触了hexo,jekyll,wordpress等快速blog生成工具，我决定自己动手打造一个自己的免费技术博客。
## 环境搭建-git下载安装
项目中用到了git并且使用的命令行工具是gitbash。首先来下载git：
* [下载git](https://git-scm.com/downloads)

选择对应自己电脑的版本下载安装，傻瓜式安装模式，一路下一步即可。

## 环境搭建-nodejs下载安装
因为Hexo是一款基于Node.js的静态博客框架，所以我们还需要安装好它：
* [下载nodejs](https://nodejs.org/en/download/)

同样选择对应自己电脑的版本下载安装，一路下一步即可。nodejs有个默认的包管理工具npm，但是由于服务器在国外【偶尔还会被墙】，所以这个项目我们使用淘宝的npm镜像cnpm，具体怎么使用cnpm参考：[淘宝 NPM 镜像](http://npm.taobao.org/)。

## hexo介绍
“A fast, simple & powerful blog framework”这是[hexo官网](https://hexo.io/)对自己的评价简单来说就是一个快速简单和高效的博客生成工具，有了它你再也不必为管理自己的博客而感到烦恼了😄。

## hexo安装
安装好git和nodejs之后，在本地新建一个文件夹hexo-test，进入该文件夹之后右键--Git Bash here。然后输入这条命令来全局安装hexo：
```
//-g 代表全局安装
cnpm install hexo -g

```
按下回车之后很快就会出现安装信息。来试试安装成功了没有，输入以下命令来确认：
```
//也可输入hexo --version[-v的全称]
hexo -v

```
如果出现以下类似命令则表示安装成功：
```
$ hexo --version
hexo: 3.3.1
hexo-cli: 1.0.2
os: Windows_NT 10.0.14393 win32 x64
http_parser: 2.7.0
node: 7.5.0
v8: 5.4.500.48
uv: 1.10.2
zlib: 1.2.8
ares: 1.10.1-DEV
modules: 51
openssl: 1.0.2k
icu: 58.2
unicode: 9.0
cldr: 30.0.3
tz: 2016j
```

## hexo的使用
恭喜你已经成功安装了，下面一步步的跟着我来使用hexo的常用命令搭建博客，想想都激动!!!
1. 初始化hexo，进入hexo-test文件夹之后右键--Git Bash here，输入：
```
hexo init

```
等待个大概十几秒钟，整个hexo就初始化完成了，最新版本的hexo在init初始化的时候就默认安装了所有的依赖包，不过为了确保万无一失，你可以输入命令：cnpm install，具体安装了哪些依赖包，可以查看hexo-test目录下的package.json文件。然后你就可以在hexo-test文件夹下看到如下工程目录：
![](http://omqvgxrwm.bkt.clouddn.com/1.jpg)

2. hexo编译生成，继续在Git Bash中输入：
```
hexo generate(可简写为：hexo g)
```
这一步就是hexo的编译生成静态文件过程，就是hexo-test目录下的public文件夹。里面就是打包编译后的网站博客静态文件（也就是你要上传到线上码云pages的文件）。
3. hexo开启本地服务器，继续输入：
```
hexo sever(可简写为：hexo s)
```
hexo 有开启本地服务器的功能，这样你就可以在[本地](http://localhost:4000)预览访问你的网站了，在浏览器中输入[http://localhost:4000](http://localhost:4000),不出意外你就可以得到如下图的hexo博客网站系统：
![](http://omqvgxrwm.bkt.clouddn.com/2.jpg)
如果和我一样出现了上图的页面，恭喜你，你已经成功拥有了自己的博客系统！！！
如果你想停止本地服务器，在git bash中按下：Ctrl+c即可。
