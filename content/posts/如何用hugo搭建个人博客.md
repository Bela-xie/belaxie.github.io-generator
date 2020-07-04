---
title: "如何用hugo搭建个人博客"
date: 2020-07-04T10:30:03+08:00
draft: false
---
因为我的电脑是Windows系统，因此此篇文章的操作仅适用在Windows系统中，对于其他系统的用户，借鉴意义不大。
# 一、安装hugo
查看[官方文档](https://gohugo.io/getting-started/installing)进行安装，以下步骤若有不清楚的地方，文档上有详细的安装步骤可进行查看。
1. 点击来到[hugo release](https://github.com/gohugoio/hugo/releases)网页，查找最新版本，找到适用于本机系统的zip文件进行下载。
2. 下载后进行解压，然后找到hugo.exe文件，复制存放该文件的路径，然后将该路径配置到本电脑的高级系统设置--环境变量--path中。例如我的存放路径为D:\Software\hugo，那么配置就如下图所示：
   ![第一张配置图](/image/1.png)
   ![第二张配置图](/image/2.png)
3. 启动终端，运行hugo version，若返回安装的版本号，则代表安装成功。
   ![第三张配置图](/image/3.png)

# 二、搭建博客
hugo官网上有很详细的步骤说明，点击进入[hugo官网](https://gohugo.io/)，点击Quick Start，启动终端，新建一个文件夹，然后依次执行官网上的step2~step7中的命令（step1已在第一步中执行），在终端运行命令的时候要注意将quick start重命名。

## step2:
新建一个文件夹，在该目录下执行命令：hugo new site name.github.io-generator，注意name是你在github上的账户名，全小写。

## step3：
进入上一步创建的目录，即依次执行cd name.github.io-generator---git init---git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke---echo 'theme = "ananke"' >> config.toml，这一步的目的是下载博客网站的主题。

## step4:
执行hugo new posts/my-first-post.md，然后编辑第一篇博客的内容。注意不要修改原有的内容，修改后要将draft改为false。

## step5：
执行hugo server -D，可进行网站的预览。

## step6：
打开config.toml文件，进行配置，要将图中的baseURL改为自己github上的网址，将languageCode改为zh-Hans，title自定义自己想要的博客名称。
![第四张图片](/image/4.png)
## step7
执行hugo -D，创建public文件。

执行完毕后会得到一个public目录，这就是我们的博客站点。如果要预览网站，那么就需要在终端上执行hugo server，不能直接打开public下的index.html文件，因为不能使用文件协议进行预览。

若要创建第二篇博客，则需要在上述创建的根目录中再次执行```hugo new posts/自定义博客题目.md```，然后打开该文件进行博客的编辑，编辑完成后执行```hugo -D```，那么在public目录中就会出现你编辑的第二篇博客啦。

若要在github pages预览html文件，请见下一篇博客^-^


