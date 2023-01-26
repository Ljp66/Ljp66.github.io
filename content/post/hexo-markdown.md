---
title: hexo-markdown
date: 2023-01-14 18:52:58
categories:
    - tech
tags:
    - hexo
---

## 插入图片
在写文章时，常常有配图说明的需求。Hexo有多种图片插入方式，可以将图片存放在本地引用或者将图片放在CDN上引用。

<!--more-->

### 本地引用
1. 统一存放
>当Hexo项目中只用到少量图片时，可以将图片统一放在`source/images`文件夹中，通过markdown语法访问它们。
>图片既可以在首页内容中访问到，也可以在文章正文中访问到。
>```markdown
>![](/images/image.jpg)
>```
2. 分散存放
>图片除了可以放在统一的images文件夹中，还可以放在文章自己的目录中。文章的目录可以通过配置`_config.yml`来生成。
>```markdown
>post_asset_folder: true
>```
>将`_config.yml`文件中的配置项`post_asset_folder`设为true后，执行命令`hexo new post_name`，在`source/_posts`中会生成文章`post_name.md`和同名文件夹post_name。将图片资源放在post_name中，文章就可以使用相对路径引用图片资源了。上述是markdown的引用方式，图片只能在文章中显示，但无法在首页中正常显示。
>```markdown
>![](image.jpg)
>```

如果希望图片在文章和首页中同时显示，可以使用标签插件语法。
```markdown
{% asset_img image.jpg This is an image %}
```
### CDN引用
除了在本地存储图片，还可以将图片上传到一些免费的CDN服务中。比如Cloudinary提供的图片CDN服务，在Cloudinary中上传图片后，会生成对应的url地址，将地址直接拿来引用即可。

## 数学公式

$$
c = \pm\sqrt{a^2 + b^2}
$$
