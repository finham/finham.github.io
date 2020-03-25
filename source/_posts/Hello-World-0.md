---
title: Hello World
date: 2020-03-25 19:53:20
tags:
---

# Github Pages搭建个人博客

## 下载node.js

下载地址：https://nodejs.org/zh-cn/download/

[Nodejs安装及环境配置](https://www.jianshu.com/p/13f45e24b1de)

* 其中会发现无法下载express，原因是需要管理员权限。即win+R是不够的，按win+X选择PowerShell管理员，照样输入就可以了。

* 下载后发现文件并没有在programfiles/nodejs下，还是在fin/appdata/下，原来是`npm config set prefix "D:\Develop\nodejs\node_global"`，`npm config set cache "D:\Develop\nodejs\node_cache"`这两句也要在管理员页面进行设置才有效。

  ["npm ERR! Error: EPERM: operation not permitted"问题解决](https://blog.csdn.net/fjnjxr/article/details/53158204)

## Git

下载地址：https://git-scm.com/

Git本来就安装了= = 就是下载安装

## Github Pages

其实就是要自己写或者用软件生成静态网页放进仓库里然后设置为Github Pages进行展示。就这样。

经过以上步骤后点击finham.github.io已经可以看到一个模板网页出来了。

## Hexo

接下来安装Hexo，在Git Bash中总是出错，错误信息如下：

```error
npm ERR! code EPERM
npm ERR! syscall open
npm ERR! path C:\Program Files\nodejs\node_cache...
npm ERR! errno -4048
npm ERR! Error: EPERM: operation not permitted, open 'C:\Program Files\'
```

那我这时候改成按`win+X`选择PowerShell管理员，输入命令就可以安装了！

命令为：-g表示全局安

```console
npm install -g hexo-cli  //-g表示全局安装
```

然后你需要创建一个空的文件夹(随便啥名字都可以，不过程序员不可以随便，还是取个好点的名字，叫hexo)，这个文件夹我建在c:/users/fin/hexo下。

在Git Bash中输入：

```console
hexo init 
```

操了执行这个后又给我出现一些错误，说Failed to install dependencies, Please run"npm install" manually

操，然后按`win+X`选择PowerShell管理员输入：

```console
npm install
```

然后你会发现文件夹下是这个样子：

```console
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

然后再使用Git Bash，输入以下命令让服务器运行起来

```console
hexo server
```

> 我算是发现了，只要是npm相关的命令，都得使用PowerShell管理员，应该是哪里没有设置权限的原因！同时在这个文件夹里我发现多加了node_modules这个文件夹！汗！

此时访问http://localhost:4000/就能看到Hexo的效果了~

## Github Desktop

下载地址：https://desktop.github.com/

接下来下载Github Desktop到本地即可。