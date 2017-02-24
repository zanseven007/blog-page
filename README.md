## 说明

本 Blog 是搭建在 Github Pages 上面的，并通过DNS解析到 [http://blog.zanyuyu.com](http://blog.zanyuyu.com/)

想进一步了解Hexo请看 [Hexo Docs](https://hexo.io/zh-cn/docs/)

### 创建一篇新文章

``` bash
$ hexo new "my-first-post"
```

执行后会输出
``` bash
INFO  Created: ~/Dev/gitcafe/dxy-biz-developer.github.io/source/_posts/my-first-post.md
```

用普通的文本编辑器打开 `dxy-biz-developer.github.io/source/_posts/my-first-post.md` 文件，就可以开始写文章了。
请遵循标准的 MarkDown 书写规范。

注：`"my-first-post"` 部分请不要用中文，请使用类似 `my-first-post` / `how-to-start-learing-php` 这样的命名形式。

更多信息：
- [Writing](https://hexo.io/zh-cn/docs/writing.html)

### 本地预览

``` bash
$ hexo server
```

默认预览链接是 `http://0.0.0.0:4000/`

更多信息：
[预览](https://hexo.io/zh-cn/docs/server.html)

### 生成静态文件

``` bash
$ hexo generate
```

### 发布

``` bash
$ hexo deploy
```
发布博客，之后会自动发布到 [https://github.com/zanseven007/blog-page](https://github.com/zanseven007/blog-page)

