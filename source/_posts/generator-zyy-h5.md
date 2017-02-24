---
title: 赞鱼鱼的H5脚手架
date: 2016-09-28 17:59:21
tags:     
    - 前端
    - 个人
    - 复制粘贴专用
---

在一个风雨交加的午后，基于工作干完后，闲的蛋疼，想着日后H5必定很火，会有很多H5的项目要做，为了方便今后的开发，告别复制粘贴，特此用yeoman写了一个由gulp和webpack打包的H5脚手架,[H5脚手架github地址](https://github.com/zanseven007/generator-zyy-h5)。

<!--more-->

本想使用gulp-tinypng打包压缩一下图片，无奈速度太慢以及其他一些bug只好放弃，还是老实的去[tinypng官网](https://tinypng.com)压缩吧。

# 基于Webpack和Gulp的H5小项目生成器

> - H5 日益普及，为了方便日后开发的方便，特此写一个模板生成器为日后使用
> - 在HTML中支持使用 @@include 引入一个 .inc 文件
> - 在CSS文件中可以使用 sass 进行开发
> - 在JS当中利用webpack合并了公共模块，可以有任意个入口文件
> - 开发时可自动启动 Chrome 浏览器，并且打开本地3000端口来调试

## 使用yoeman创建模板
安装 yo

```
npm install -g yo
```
安装H5模板生成器

```
npm install -g generator-zyy-h5
```
新建一个项目目录并进入

```
mkdir my-new-h5 && cd $_
```
使用H5模板

```
yo zyy-h5
```

## 使用模板
开发

```
gulp dev
```
发布(会压缩css和js，并增加md5)
```
gulp dist
```

## ISSUE

**node-sass安装失败解决办法**：因为在安装`node-sass`的时候它把github Releases里的文件都托管在`s3.amazonaws.com`上面，而这个网址在国内总是网络不稳定，所以我们通过淘宝镜像去下载这个文件。

直接运行下面的命令即可

```
SASS_BINARY_SITE=https://npm.taobao.org/mirrors/node-sass/ npm install node-sass
```

## License
MIT © [zanseven007](https://github.com/zanseven007)
