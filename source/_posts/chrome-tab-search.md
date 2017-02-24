---
title: Chrome的Tab键搜索功能探索
date: 2016-11-02 16:31:33
tags:
    - 前端
    - 个人
    - chrome
---
一直在使用chrome的地址栏tab快速搜索功能，一直不知道其实现方式，在一个闲的蛋疼的日子，探索了一下其中的奥秘，并给自己博客加入了tab搜索功能。
<!--more-->
## 这个功能是什么？

我们打开浏览器，然后再地址栏输入www.baidu.com，如下图：

![步骤1](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-1.jpg)

然后按下tab键，并输入`百度sb`：

![步骤2](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-2.jpg)

之后敲下回车就出现了我们想要的结果：

![步骤3](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-3.jpg)

是不是很简单呢？其实这是使用了chrome自身的搜索引擎，可以在chrome设置里面添加你自己想要的快捷tab搜索，但是这只对你自己一个人的浏览器生效。

![步骤4](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-4.jpg)

** 可是百度是如何做到帮我的浏览器自动添加快捷搜索的呢？**

探索后发现百度是在网页的head里引入了一个type为 `application/opensearchdescription+xml` 的xml文件，如下图：

![步骤5](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-5.jpg)

这个xml文件很简单，里面就几行代码：

![步骤6](http://oddd7fcxh.bkt.clouddn.com/chrome-tab-search/tab-6.jpg)

这里面的 `ShortName` 就是按下tab后所要显示的名字，这里面有个`{searchTerms}` 这个便是搜索关键字变量，可按照情况将url标签的链接换成你网站的搜索链接。

在这儿附上我的xml代码:

```html
<?xml version="1.0" encoding="UTF-8"?>
<OpenSearchDescription xmlns="http://a9.com/-/spec/opensearch/1.1/">
  <InputEncoding>utf-8</InputEncoding>
  <ShortName>赞鱼鱼的博客</ShortName>
  <Description>做一个最gay的程序猿</Description>
  <Image height="16" width="16" type="image/x-icon">http://7xljz9.com1.z0.glb.clouddn.com/favicon.ico</Image>
  <Url type="text/html" template="https://www.google.com/webhp#q=site%3Ablog.zanyuyu.com%20{searchTerms}"/>
</OpenSearchDescription>

```

*因为hexo不支持站内搜索，所以我将tab搜索指引到了谷歌搜索*
*知乎，淘宝，微博，A站，B站等N多网站都支持chrome tab搜索*