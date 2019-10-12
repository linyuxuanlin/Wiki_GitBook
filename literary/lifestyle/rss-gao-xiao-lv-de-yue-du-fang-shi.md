# RSS - 高效率的阅读方式

## RSS 是什么

RSS 的全称是「简易内容聚合」（Really Simple Syndication），是一个能让你在一个地方订阅各种感兴趣网站的工具。

> 一个网站支持 RSS，就意味着每当它新发布一篇新文章，就会往一个位于特定网址的文件中，以特定的语法（具体而言是 XML 标记语言或 JSON）增加一条记录，列明这篇文章的标题、作者、发表时间和内容（可以是全文，也可以是摘要）等信息。这样，用户只要搜集所有他感兴趣的网站提供的这种文件的网址，并不时检查这些文件内容的更新，就能知道这些网站是否、何时发布了什么内容。RSS 阅读器的核心功能，就是存储用户订阅的 RSS 地址，以固定的频率自动检查更新，并将其内容转换为易读的格式呈现给用户。

简单地说，当我关注的某个人在知乎、或者在博客上回答了一个问题、写了一篇新文章，我马上就能收到推送。当我关注的人变多了，我不必一一点开知乎、简书、甚至翻看博客去主动获取更新，而是在一个统一的终端内阅读。

## 为什么用 RSS

RSS 的对立面是算法推荐，像微信公众号、知乎、微博、今日头条等平台。 且不说算法推送平台广告多，迁移麻烦的问题。算法推荐的特点是，你不需要刻意选择，算法会根据你的喜好，给你推送内容。这样一来，你几乎没有选择的余地，在不断被「喂饱」中逐渐失去判断的能力。更可怕的地方在于，**它替你定义了你的画像，然后把你潜移默化中变成了它所认为的你**。「大数据杀熟」的东窗事发绝非偶然，用算法窥视用户隐私是当今互联网公司的通配。

**做信息的主人，而不是奴隶。**RSS 是一种公开的协议，可自由更换平台与客户端。重要的一点是，**获取信息的权力完全自治**。RSS 相比算法推荐，拥有了可控性和安全感，隐私完全掌握在自己手里。

## 开始 RSS 阅读

### 1. 获取内容的 RSS 源

这儿分两类网站：有 RSS，无 RSS 如何判断一个网站有无 RSS，首先在网站里寻找这个标识：

![](https://picgo-1253965369.cos.ap-guangzhou.myqcloud.com/rss.png)

如果有的话，可以直接拷贝链接订阅。 没有标识呢？也可能是有 RSS 的，不过藏得比较深。

简单的方法是：直接在主域名后加 `/feed` ， `/rss` 或 `/atom.xml` 比如我的博客：[yxrct.com](https://yxrct.com) 在后面加 `/feed` 变为 [yxrct.com/feed](https://yxrct.com/feed) ，如果能刷出来一个`xml`页面，那么只需添加这个链接到 RSS 阅读器中，即可订阅。 但一些网站并不用普通的后缀，这时候我们需要用到 RSS+ 浏览器插件。

RSS+ 浏览器插件：

* 先安装 [油猴插件](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo) ，这里需要科学上网。
* 再安装 [RSS+ 脚本](https://greasyfork.org/zh-CN/scripts/373252-rss-show-site-all-rss)
* 此时，如果网站有 RSS，可在右下角小圆圈里发现。

对无 RSS 的网站，需要自己制作 RSS，这里推荐几个工具：

* [feed43](http://feed43.com/)
* [RSSHub](https://docs.rsshub.app/#%E5%BE%AE%E5%8D%9A)
* [FeedOcean](https://feedocean.com/?lang=zh-CN)

以上的工具，不仅可以订阅无 RSS 的博客，还能直接订阅知乎专栏、公众号、微博、贴吧、即刻等。具体方法参见文档。

### 2. 选择一个 RSS 阅读器

**Inoreader** 免费版基础功能完善，抓取时间大概15分钟，符合要求。有网页版、iOS、Android 版本。

**Reabble** 基于 Inoreader 的 API 开发，为 Kindle 而生。建议升级收费版（年费 ¥21，免费版 7 篇文章 / 天，且不支持推送） 我设置每天 9 点定时推送新文章至 Kindle 阅读，也方便标注 & 导出书摘。 若想在电脑上阅读，也可以直接打开 [reabble.com](reabble.com) ，创建桌面快捷方式，界面比 Inoreader 简洁且无广告。

## 订阅一些有意思的源

RSS 并不适合订阅新闻类网站，刷新太快、内容繁琐反而导致阅读体验不佳。所以 RSS 更适合订阅**高质量博客**之类的网站。订阅源并不是越多越好，应该小而精。过多的订阅源会引起「信息过载」，你会发现自己每天都收到数以百计的新资讯，却无暇阅读。

我导出了自己的订阅源，可以参考一下： [**我的订阅**](https://yxrct-1253965369.cos.ap-guangzhou.myqcloud.com/files/Inoreader%20Subscriptions%2020190211.xml)

## FAQ

Q：RSS 阅读会不会被时代淘汰？   
A：读书这种方式也没有被时代淘汰。一个趋势是，凡是互联网平台，总是向群众「喜闻乐见」喜闻乐见的方向发展，直至内容变水，新的平台取而代之，像是知乎和豆瓣。而 RSS 不受平台兴衰的影响，除非有更好的协议出现，否则 RSS 不会被淘汰。

## 总结

引用「[notajerk](https://sspai.com/user/701048/updates)」的话结尾：

> 在网上获取信息时，可以中二一点把自己想象成古代听取群臣意见的帝王。对于皇帝来说，最危险和最不该做的事情就是暴露自己的喜好，这是被臣下蒙蔽乃至最后被夺权篡位的基础。英明的皇帝会保持内心的虚静无为（客观中立），坚持单独听取各方意见而不暴露自己的感想，并将各方意见与客观事实一一验证来确认各自的可信度。这也是几千年后每个人获取信息时应该坚守的原则。**挑选信息来源也是最值得花时间的地方**。

## 参考与致谢

* [使用 RSS 可以做什么你未曾想过的事](https://sspai.com/post/34280)
* [怎样查找一个网站的 RSS 地址？用 RSS + ！](https://blog.wizos.me/20181022-258.html)
* [RSS 工具大全](https://blog.wizos.me/20180412-134.html)
* [【RSS】我的RSS使用介绍](https://www.cnblogs.com/buwuliao/p/8379549.html)
* [自制全文RSS汇总（附 推荐工具）](https://www.douban.com/note/522518464/)
* [论 RSS 的「复兴」](https://sspai.com/post/43998)
