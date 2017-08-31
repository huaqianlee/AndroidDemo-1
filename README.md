# AndroidDemo-Kotlin
>此README由我摘自原作者简书文章：[分享我学习Androd开发过程中写的小项目](http://www.jianshu.com/p/9d5724db30fe)

# 6个小项目
![](http://upload-images.jianshu.io/upload_images/1281203-63ebd9f6b502510d.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这6个小项目从上下到依次是天气，小说，美图，五笔查询，花瓣和2048 AI版。
下面一个一个说起

## Weather
![](http://upload-images.jianshu.io/upload_images/1281203-6700d20278f37ccb.gif?imageMogr2/auto-orient/strip)
Weather是学习Android最经典的Android学习入门书《第一行代码》的最终实战，这个例子覆盖的知识点非常全面，有网络请求，Json转换成Model，抽屉布局，DataSupport数据库的使用还有Service服务，作为入门的实战APP实在是再适合不过了。书上是用Java写的，我在这里全部使用了Kotlin来实现。代码更加精简些。

## Novel 小说阅读
![](http://upload-images.jianshu.io/upload_images/1281203-2ed6747ddf6ad36e.gif?imageMogr2/auto-orient/strip)
我有很多同事都是小说狂人，但是貌似很多小说APP都有广告(我不看小说不清楚)，于是让帮忙写个小说APP，他用都用iPhone，于是我写了个iOS版本的小说阅读APP iOS小说阅读器，然后我再想试试写一个Android版本的，于是就有了这个小项目，
![](http://upload-images.jianshu.io/upload_images/1281203-8e32a2053dcaf50c.gif?imageMogr2/auto-orient/strip)
BaseQuickAdapter真的很强大，解决了很多RecyclerView的实际需求，比较下拉刷新和加载更多等。书签用DataSupport保存，这个小项目没有使用到接口，是解析HTML实现的。使用了Jsoup来解析HTML，非常好用。另外在开发过程了还碰到了BGK问题，需要用到字符串bytes。问题不大。总之整个项目比较简单，很容易看懂。

## 美图
![](http://upload-images.jianshu.io/upload_images/1281203-c36a3a930184a3e4.gif?imageMogr2/auto-orient/strip)
![](http://upload-images.jianshu.io/upload_images/1281203-dd62ceeee2cbf379.gif?imageMogr2/auto-orient/strip)
![](http://upload-images.jianshu.io/upload_images/1281203-e7e27992eb42be93.gif?imageMogr2/auto-orient/strip)
无意中发现个网站，里面的图片质量还算不错，用来当壁纸比较合适。还可以用分辨率筛选。于是下载了他们官方的APP，但是官方APP有广告，而且好像只能看手机壁纸，不能看电脑的。这两点让我非常不爽。于是我就想自己写一个APP，无广告，可以随意收藏和下载高清壁纸。感觉很不错

开发的技术难点并不多，使用和小说阅读器一样的技术。图片显示用了Fresco，图片下载用了Glide。

## 五笔查询
![](http://upload-images.jianshu.io/upload_images/1281203-b8d6be6cf4ddafae.gif?imageMogr2/auto-orient/strip)
笔者是一个五笔使用者，虽然用了很久五笔了，但还是有很多字不会打，所以我一般在我手机上安装了五笔反查这个APP，本来作为简单的查询APP，应该十分简洁的，但是里面的广告非常让我不爽，而且非常容易点到。体验也做得比较次。比如历史查询功能就做得很一般。所以我干脆自己写一个。

这个小项目没有特别的技术难点，唯一的难点度不在于APP，而是查询网站令人蛋疼的编码，全部采用GBK编码，而且对请求和请求体有一些特殊要求。请求时需要加上这些参数，查询的文字需要用UrlEncode进行GBK编码，然后再和key拼起来。探索这结东西花了些时间。

## 花瓣
![](http://upload-images.jianshu.io/upload_images/1281203-fb584fa0da520ec4.gif?imageMogr2/auto-orient/strip)
![](http://upload-images.jianshu.io/upload_images/1281203-1b7e37312ac8a70b.gif?imageMogr2/auto-orient/strip)
![](http://upload-images.jianshu.io/upload_images/1281203-f430ea302a8643dc.gif?imageMogr2/auto-orient/strip)
![](http://upload-images.jianshu.io/upload_images/1281203-60b70ae21a34631b.gif?imageMogr2/auto-orient/strip)
花瓣APP也算了个中型的APP了，我是按照Github的花瓣 开源项目来写的，主是要学习里面的架构写法。实现了收集，登录，喜欢，搜索等功能，原作者说全部采用目前最新的和最热门技术。所以还是有一定有学习价值的。你可以把我写的这个看成是Kotlin的实现版本。但是里面关于Fragment的实现机制不一样，我用了BaseQuickAdapter,所以会比较简单些。

技术方面用了[RxJava/RxAndroid]实现异步响应，简化了很多异步回调的代码。网络方面使用了Retrofit，搭配RxJava很实用，处理数据转化成Model一步到位。其他有兴趣的可以参考代码自己实现一次，就能明白里面的架构和技术了。

## 2048 AI版
![](http://upload-images.jianshu.io/upload_images/1281203-15f4e1876e2052e6.gif?imageMogr2/auto-orient/strip)
2048是一款具有魔力的游戏，很容易上瘾。一玩就停不下来。但是我水平很菜，从来没有合出来2048。既然我合不出来，就让AI来帮忙吧。于是我参考了2048的AI实现资料，目前网络上最主流的是算法是MixMax算法，请参考文章 2048 AI 程序算法分析,里面详细地分析了这个算法，并且给出了js的实现。于是我也想在APP上实现这个算法，首先我要找到2048在安卓上在实现。我找到了这个Android版2048游戏视频教程源码,这个APP写得非常好，还有作弊和撤销功能。我就用这个APP的源码，并把它用Kotlin重新实现了一遍。然后再添加AI功能。AI的源代码我参考了2048 AI的实现。发现里面的2048实现机制和安卓机制很像，在这个基础上加上AI代码应该不难。事实上确实如此，很快我就把AI代码移植过去并成功运行。经过简单的调试后再测试了很多次，合出2048豪无压力，只是.....我不明白为何一但AI合出2048后突然就智障了，后面的每一步都像自杀一样，豪无章法。很快就挂了。目前工作还比较忙，有时间我再看看为何会这样。

技术方面最主要就是2048的AI算法以及在Android上使用Kotlin的实现2048。这又是比较大的一块，我将专门写一篇文章来说明这个AI算法和实现代码。

到目前为止，我已经开发过iOS项目，Android项目，小型Windows App项目 参考Windows APP时钟和Web项目(参考上一篇文章的Vue和Node实现的完整Blog项目)，微信公众号和小程序也有了解过，后端的话用过ASP.Net和Node.js。对目前最主流和开发平台的开发技术都有一定的了解。如果读者想进入这个行业但又不知道选择哪个平台来入门，又或者读者已经熟悉了一个平台，想再选择学习另一个平台的技术，但是不知道选哪个好，那么可以联系我。我会帮助读者结合自己的兴趣和已有知识再加上目前各平台的行情选择一个合适的平台技术学下去。

作者：黑暗中的孤影
链接：http://www.jianshu.com/p/9d5724db30fe
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
