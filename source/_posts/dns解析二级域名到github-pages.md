---
title: dns解析二级域名到github pages
date: 2016-09-12 10:13:17
tags:
    - 前端
    - github
    - 网络
---

今天把原先放在github pages上的简历网站，博客网站都转到了自己的域名www.zanyuyu.com的二级域名下（简历：[赞鱼鱼的简历](http://resume.zanyuyu.com)和博客：[赞鱼鱼的填坑生活](http://blog.zanyuyu.com)）, 趁着现在工作没任务，把实现过程写下来。

<!--more-->

### 配置CNAME

如果要将github pages 提供的默认域名解析到自己的域名，就需要在github 仓库下新建一个CANME文件如下图所示：

![CNAME](http://oddd7fcxh.bkt.clouddn.com/CNAME.png)

之后在CNAME文件中填写你自己的域名:

![CANME-content](http://oddd7fcxh.bkt.clouddn.com/CNAME-content.png)

最后只需要去你使用的DNS解析网站添加一条记录值即可：

![dsn-setting](http://oddd7fcxh.bkt.clouddn.com/dns-setting.png)
*注意的是记录类型需要选择为CNAME*

之后就需要稍等10分钟左右就可以使用[blog.zanyuyu.com](http://blog.zanyuyu.com) 来访问 原来的zanseven007.github.io/blog-page了。