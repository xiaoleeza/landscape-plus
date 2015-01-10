# Landscape plus (Fork from [xiangming/landscape-plus](https://github.com/xiangming/landscape-plus))

针对中国大陆地区对hexo官方主题landscape进行优化。

## 所有新特性
+ 增加返回顶部按钮，也可取消
+ 增加站长统计代码
+ 更改站内搜索为swiftype
+ 修改tagcloud显示数量
+ 根据国情，**去掉Google的库**，改用cloudflare的cdn，打开页面不再卡住了。=> [参与国内cdn的讨论](https://github.com/xiangming/landscape-plus/issues/3)
+ 增加了 **语言包** 。（支持英文、中文简体和中文繁体。）
+ 增加了 **友情链接** widget。（已默认开启，修改方法看下面的[常见问题](#常见问题)。）
+ 修改了原主题的 **配色** 和部分markdown样式（blockquote/code...）
+ 集成 **多说评论模块** 。（开启方法看下面的[常见问题](#常见问题)。）
+ 集成 **百度分享模块** 。（默认不开启，已知[BUG](https://github.com/xiangming/landscape-plus/issues/42)，所以把原分享修改成了国内SNS。）
+ 增加对 **IE8** 的支持。
+ 集成 **mathjax**，即latex数学公式的支持。（感谢 @Svtter 的[pull request](https://github.com/xiangming/landscape-plus/pull/35)）

主题还在调整中，欢迎[new issue](https://github.com/Beeder/landscape-plus/issues/new)来提建议，参与讨论。

## 文档目录

+ [演示](#演示)
+ [安装](#安装)
+ [启用](#启用)
+ [更新](#更新)
+ [配置](#配置)
+ [常见问题](#常见问题)

## <a name='演示'>演示</a>

你可以点击[这里](http://beeder.me/)，查看演示。

## <a name='安装'>安装</a>

``` bash
$ git clone https://github.com/Beeder/landscape-plus.git themes/landscape-plus
```
**Landscape plus 需要 Hexo 2.7 及以上版本.**

## <a name='启用'>启用</a>

修改主题的设置文件`_config.yml`，把`theme`的值设置为`landscape-plus`

## <a name='更新'>更新</a>

``` bash
cd themes/landscape-plus
git pull
```

## <a name='配置'>配置</a>

```yml
# Header
menu:
  Home: /
  Archives: /archives
  About: /about
rss: /atom.xml

# Content
excerpt_link: Read More
fancybox: true

# Sidebar
sidebar: right
widgets:
- category
- tag
- tagcloud
- archive
- recent_posts
- links

# Links
links:
  Beeder: http://beeder.me/

# Miscellaneous
google_analytics:
favicon: /favicon.png
twitter:
google_plus:
fb_admins: 
fb_app_id:

#Weibo ID. e.g. 436062867 for http://weibo.com/436062867
weibo_id:  

# Duoshuo
duoshuo_shortname: 

# Baidu share
baidushare: false

#Back To Top
back_to_top: true

#Swiftype
Swiftype: true
```

+ `links` - 友情链接
+ `duoshuo_shortname` - 多说评论id
+ `baidushare` - 是否开启百度分享
+ `back_to_top` - 是否添加返回顶部按钮
+ `Swiftype` - 站内搜索是否使用Swiftype

## <a name='常见问题'>常见问题</a>

**问**：Demo看起来很赞，我要**怎么使用landscape+主题？**
> 按照上方的步骤进行`安装`、`启用`、`更新`。

**问**：怎么提建议？
> 主题还在调整中，欢迎[new issue](https://github.com/Beeder/landscape-plus/issues/new)来提建议，参与讨论。

**问**：怎么添加友情链接？
> 修改`themes/landscape-plus/_config.yml`中的`links`。

**问**：我是中国人，我要使用中文？
> 配置你的hexo源文件的`_config.yml`，添加`language: zh-CN`。

**问**：如何开启多说评论模块？
> 修改`themes/landscape-plus\_config.yml`，填写你的多说id即可。（主题会自动启用多说评论，忽略hexo默认的disqus。）

**问**：如何开启百度分享模块？
> 修改`themes/landscape-plus\_config.yml`，将`baidushare`设置为`true`即可。（已默认关闭，已知[BUG](https://github.com/xiangming/landscape-plus/issues/42)，所以把原分享修改成了国内SNS。）

**问**：如何使用RSS分享功能？
> 请参考这条[issue](https://github.com/xiangming/landscape-plus/issues/31)进行配置。

**问**：如何增加返回顶部按钮？
> 修改`themes/landscape-plus\_config.yml`，将`back_to_top`设置为`true`即可。（已默认开启）

**问**：如何修改站内搜索为Swiftype？
> 修改`themes/landscape-plus\_config.yml`，将`Swiftype`设置为`true`，并在Swiftype官网选择overlay的needs a search field类型，将搜索代码粘贴在`..\theme\landscape-plus\layout\_partial\header.ejs`注释处。

**问**：weibo_id是什么东西？
> 填写weibo_id，在别人分享你的文章到微薄时，会自动@你，weibo_id是一串数字，在[这里](http://open.weibo.com/sharebutton)第一步的关联账号中填写你的微薄账号，在第三步的WBML代码中显示的`ralateUid`即为你的weibo_id。

**问**：站长统计代码贴在哪里？
> 修改`..\theme\landscape-plus\layout\_partial\footer.ejs`，将最简洁的站长统计代码粘贴在注释处。

**问**：怎样自定义标签云显示标签数量？
> 修改`..\theme\landscape-plus\layout\_widget\tagcloud.ejs`第5行，将amount设置为想要显示的标签数，0为全部显示。

**问**：怎么修改代码高亮样式？
> 修改`..\theme\landscape-plus\source\css\_partial\highlight.styl`，样式代码看[这里](https://github.com/isagalaev/highlight.js/tree/master/src/styles)。

关于`Hexo`及其主题的详细内容，可以看[博客搬家，从Jekyll到Hexo](http://beeder.me/2014/12/11/new-blog-from-jekyll-to-hexo)。