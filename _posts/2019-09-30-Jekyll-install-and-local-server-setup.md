---
layout: post
title:  "Jekyll install and local server set up"
date:   2019-09-10 4:06:54
categories: wed_develop
tags: jekyll git
excerpt: 安装Jekyll以及建立github静态网页
mathjax: true
---


### 1. 安装 Ruby
首先，点击下面的按钮，下载与您的系统架构（x86 / x64）相匹配的Ruby安装程序。

[Ruby Windows 下载](https://rubyinstaller.org/downloads/) 选择同时安装 Ruby DevKit。 Jekyll具有一些依赖性，即开箱即用，只提供原始源代码，为了使其成为完全功能的可执行文件，需要安装开发工具包。

### 2. 打开ruby shell

`gem -h`

> 测试安装是否成功

### 3. 安装bundler

    gem install bundler

> Bundler: The best way to manage a Ruby application's gems

### 4. 安装Jekyll

gem install jekyll

  

### 5. 安装 jekyll-paginate

在cmd中输入：

    gem install jekyll-paginate

### 6. 验证安装完成

在cmd中输入：

 `jekyll -v`


###  7. 开启本地实时预览

切换到仓库所在目录，在cmd中输入:

`jekyll serve`

###  8. 安装git, 连接github账户

启动git, 建立密钥

    ssh-keygen -t rsa -C "xxx@126.com"

 
###  9.将id_rsa.pub密钥填写到 github账户ssh 设置

    cat ~/.ssh/id_rsa.pub

以ssh-rsa开头

  
###  10.将远程厂库克隆到本地

    git clone git@github.com:xxx.git

  
###  11， 进入 ~/github/fengpku.github.io 目录

启动本地网页服务

    git serve

出现错误，根据提示运行

    gem update

在Gemfile中添加

    source 'https://rubygems.org'

之后运行

 `bundle install --no-deployment`

###  12. 启动本地网页服务

    bundle exec jekyll serve

###  13.搭建博客所遇到的问题

搭建个人博客，jekyll框架提供了许多丰富的功能，也为我们省去许多麻烦。我们可以直接clone别人的模范，然后上传至自己的远程仓库去进行托管。但是，在制作个人博客时，遇到棘手的问题也真不少，好在逐个都解决了。

下面，列出自己在搭建个人博客时所遇到一些问题。

- 问题 1

> Could not load Bundler. Bundle install skipped.

接着使用jekyll serve 的时候提示没有运行所需的buddle，从stackoverflow上找到的答案：使用 “gem install kekyll bundle” 便可解决。
- 问题 2
> Could not find public_suffix-3.0.0 in any of the sources
> (Bundler::GemNotFound)

如果将别人的项目直接clone下来，许多时候都会出现如上所示的错误。查阅资料发现，这是导致自身配置路径出现混乱而出现的问题。因此可以通过命令’ bundle install –path vendor/cache ’ or ’ bundle install --no-deployment ’ 去重新修正。

- 问题 3

> You have already activated public_suffix 3.0.2,but your Gemfile
> requires public_suffix 3.0.0. Prepending `bundle exec` to your command
> may solve this. (Gem::LoadError)

在解决问题 1 之后，这应该不算问题。此时只需执行” bundle exec jekyll serve “去启动服务器即可解决。（在这之前若一直使用 ‘jekyll s’ 启动，之后稍加注意即可。） 

上述所提到的，可以解决搭建过程中的许多问题。接着，简单提下具体步骤：
1. 打开此电脑，选择一个文件夹，比如 f 盘的 test 文件，右键空白处点击 git bash here, 将该文件在终端打开；
2. 执行命令git clone, git@github.com:tzhou2018/tzhou2018.github.io.git 将远程仓库clone下来
3. 对 clone 下来的文档进行局部修改，然后提交上去。
注意：提交过程可能会出错，根据提示一步步去改错。使用上文提到的解决方法应该可以解决。
原文链接：https://blog.csdn.net/ZT7524/article/details/81638867







