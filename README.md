# 本仓库只用于备份博客，和修改版本

主题[butterfly][1] 版本4.1.0

官方文档[https://butterfly.js.org/][2]

[外挂标签使用文档][3]

使用1.4及后续更新的需要配置开启评论不然会有bug

[1]: https://github.com/jerryc127/hexo-theme-butterfly.git
[2]: https://butterfly.js.org/posts/21cfbf15/
[3]: https://www.npmjs.com/package/hexo-butterfly-tag-plugins-plus

## 修改目录

1. 2022/8/15 初始版本
2. 2022/8/15 修改内容如下
 * 整合css并以_custom加载css
 * 修改整体，背景调整为透明，并添加安卓(白夜)电脑(白夜)背景图
 * 在页脚添加了🦋特效
 * 添加的动态title
3. 2022/8/17
 * 修复背景pjax bug
 * 修改背景图片调整图片位置
 * 新增留言板
 * 新增站点公祭日自动变灰
 * 新增底部页脚电子钟计时(原生)
4. 2022/8/18
 * 新增外挂标签
 * 替换hexo自带编译器
 * 修改友联样式(需要在\source\_data\link.yml中添加一条siteshot配置选项)
5. 2022/8/19
 * 自定义版权说明
 * 修改文章页面上下篇
6. 2022/8/22
 * 添加白天夜间模式转换动

## 文件结构

此文件结构只存在于[butterfly][1]，并只会列出已修改的文件

```
butterfly
 |_languages
 |_layout
  |_includes
   |_custom
    |_sun_moon.pug --1.5新增，svg动画
   |_page
    |_flink_style --1.3新增，友联样式风格
     |_butterfly.pug --1.3新增，友联样式
     |_flexcard.pug --1.3新增，友联样式
     |_volantis.pug --1.3新增，友联样式
    |_flink.pug --1.3修改，将资源指向flink_style
   |_post
    |_post-copyright.pug --1.4修改，修改版权样式
   |_third-party
    |_pjax.pug --1.2修改，修复背景pjax
   |_footer.pug --1.1修改，页脚修改
   |_head.pug --1.5修改，动画样式
   |_layout.pug --1.1修改，增加PC端的白天黑夜双背景
   |_pagination.pug --1.4修改，调整文章上下篇布局
   |_rightside.pug --1.5修改，替换昼夜切换按钮
 |_scripts
 |_source
  |_css
   |__custom --1.1新增，魔改css引入文件夹
    |_colour.css --1.1新增，修复以及修改背景透明和黑夜模式bug
    |_custom.css 1.1新增，底部蝴蝶特效
   |__layout
    |_fixed-pagination.styl --1.4新增，文章页上下篇UI
    |_post.styl --1.4修改，版权样式
    |_sun_moon.styl --1.5新增，添加白天夜间模式转换动按钮样式
    |_web-bg.styl --1.1新增，增加手机端的白天黑夜双背景
   |__page
    |__flink_style
     |_butterfly.styl --1.3新增，友联样式
     |_flexcard.styl --1.3新增，友联样式
     |_volantis.styl --1.3新增，友联样式
    |_flink.styl --1.3修改，资源指向_flink_style
   |_index.styl --1.1修改，调整了css引入
   |_var.styl --1.1修改，接入修改
  |_js
   |_diytitle.js --1.1新增，动态title
   |_fixed-pagination.js --1.4新增，滚动监测
   |_grayscale.js --1.2新增，站点公祭日自动变灰
   |_sun_moon.js --1.5新增，去除了冗余代码，去jquery
 |__config.yml --主题配置文件
 
```

## _config.yml修改内容

1. 1.1修改

```
# Website Background (設置網站背景)
# can set it to color or image (可設置圖片 或者 顔色)
# The formal of image: url(http://xxxxxx.com/xxx.jpg)
background:

//修改为

# Website Background (設置網站背景)
# can set it to color or image (可設置圖片 或者 顔色)
# The formal of image: url(http://xxxxxx.com/xxx.jpg)
background:
  default: url(https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/c809cc53e7217a70801eee6dd76926a0_compress72.jpg) #【必选】默认背景
  darkmode: url(https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/bf33ad56eb7b93e6aff45c8dc730e72c_compress0.jpg) #【可选】PC端夜间模式背景
  mobileday: url(https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi@1.0.1/turing_20220614-084252_compress75.jpg) #【可选】移动端日间默认背景
  mobilenight: url(https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/turing_20220614-085038_compress11.jpg) #【可选】移动端夜间模式背景

//新增css，js

inject:
  head:
  bottom:
    # 阿里矢量图标
    - <script async src="//at.alicdn.com/t/font_2032782_8ns648avijk.js"></script>
    # 动态title
    - <script async src="/js/diytitle.js"></script>

```

2. 1.2修改

```

//1.2新增留言板，为了防止npm背刺将资源上传到b2网盘

# envelope_comment
# see https://akilar.top/posts/e2d3c450/
envelope_comment:
  enable: true #控制开关
  custom_pic:      
    cover: https://file.pigax.cn/hexo-butterfly-envelope/lib/violet.jpg #信笺头部图片
    line: https://file.pigax.cn/hexo-butterfly-envelope/lib/line.png #信笺底部图片
    beforeimg: https://file.pigax.cn/hexo-butterfly-envelope/lib/before.png # 信封前半部分
    afterimg: https://file.pigax.cn/hexo-butterfly-envelope/lib/after.png # 信封后半部分
  message: #信笺正文，多行文本，写法如下
    - 有什么想问的？
    - 有什么想说的？
    - 有什么想吐槽的？
    - 哪怕是有什么想吃的，都可以告诉我哦~
  bottom: 自动书记人偶竭诚为您服务！ #仅支持单行文本
  height: #1050px，信封划出的高度
  path: #【可选】comments 的路径名称。默认为 comments，生成的页面为 comments/index.html
  front_matter: #【可选】comments页面的 front_matter 配置
    title: 留言板
    comments: true

//留言板原版

# envelope_comment
# see https://akilar.top/posts/e2d3c450/
envelope_comment:
  enable: true #控制开关
  custom_pic:      
    cover: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/violet.jpg #信笺头部图片
    line: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/line.png #信笺底部图片
    beforeimg: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/before.png # 信封前半部分
    afterimg: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/after.png # 信封后半部分
  message: #信笺正文，多行文本，写法如下
    - 有什么想问的？
    - 有什么想说的？
    - 有什么想吐槽的？
    - 哪怕是有什么想吃的，都可以告诉我哦~
  bottom: 自动书记人偶竭诚为您服务！ #仅支持单行文本
  height: #1050px，信封划出的高度
  path: #【可选】comments 的路径名称。默认为 comments，生成的页面为 comments/index.html
  front_matter: #【可选】comments页面的 front_matter 配置
    title: 留言板
    comments: true

//1.2新增，页脚电子钟计时(原生)，为了防止npm背刺将资源上传到b2网盘

# footer_beautify
# 页脚计时器：[Native JS Timer](https://akilar.top/posts/b941af/)
# 页脚徽标：[Add Github Badge](https://akilar.top/posts/e87ad7f8/)
footer_beautify:
  enable:
    timer: true # 计时器开关
    bdage: true # 徽标开关
  priority: 5 #过滤器优先权
  enable_page: all # 应用页面
  exclude: #屏蔽页面
    # - /posts/
    # - /about/
  layout: # 挂载容器类型
    type: id
    name: footer-wrap
    index: 0
  # 计时器部分配置项
  runtime_js: https://file.pigax.cn/hexo-butterfly-footer-beautify/lib/runtime.js
  runtime_css: https://file.pigax.cn/hexo-butterfly-footer-beautify/lib/runtime.css
  # 徽标部分配置项
  swiperpara: 3 #若非0，则开启轮播功能，每行徽标个数
  bdageitem:
    - link: https://hexo.io/ #徽标指向网站链接
      shields: https://img.shields.io/badge/Frame-Hexo-blue?style=flat&logo=hexo #徽标API
      message: 博客框架为Hexo_v5.4.0 #徽标提示语
    - link: https://butterfly.js.org/
      shields: https://img.shields.io/badge/Theme-Butterfly-6513df?style=flat&logo=bitdefender
      message: 主题版本Butterfly_v3.8.2
    - link: https://www.jsdelivr.com/
      shields: https://img.shields.io/badge/CDN-jsDelivr-orange?style=flat&logo=jsDelivr
      message: 本站使用JsDelivr为静态资源提供CDN加速
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Vercel-brightgreen?style=flat&logo=Vercel
      message: 本站采用双线部署，默认线路托管于Vercel
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Coding-0cedbe?style=flat&logo=Codio
      message: 本站采用双线部署，联通线路托管于Coding
    - link: https://github.com/
      shields: https://img.shields.io/badge/Source-Github-d021d6?style=flat&logo=GitHub
      message: 本站项目由Github托管
    - link: http://creativecommons.org/licenses/by-nc-sa/4.0/
      shields: https://img.shields.io/badge/Copyright-BY--NC--SA%204.0-d42328?style=flat&logo=Claris
      message: 本站采用知识共享署名-非商业性使用-相同方式共享4.0国际许可协议进行许可
  swiper_css: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.css
  swiper_js: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.js
  swiperbdage_init_js: https://npm.elemecdn.com/hexo-butterfly-footer-beautify/lib/swiperbdage_init.min.js

//页脚电子钟计时(原生)原版

# footer_beautify
# 页脚计时器：[Native JS Timer](https://akilar.top/posts/b941af/)
# 页脚徽标：[Add Github Badge](https://akilar.top/posts/e87ad7f8/)
footer_beautify:
  enable:
    timer: true # 计时器开关
    bdage: true # 徽标开关
  priority: 5 #过滤器优先权
  enable_page: all # 应用页面
  exclude: #屏蔽页面
    # - /posts/
    # - /about/
  layout: # 挂载容器类型
    type: id
    name: footer-wrap
    index: 0
  # 计时器部分配置项
  runtime_js: https://npm.elemecdn.com/hexo-butterfly-footer-beautify@1.0.0/lib/runtime.js
  runtime_css: https://npm.elemecdn.com/hexo-butterfly-footer-beautify@1.0.0/lib/runtime.css
  # 徽标部分配置项
  swiperpara: 3 #若非0，则开启轮播功能，每行徽标个数
  bdageitem:
    - link: https://hexo.io/ #徽标指向网站链接
      shields: https://img.shields.io/badge/Frame-Hexo-blue?style=flat&logo=hexo #徽标API
      message: 博客框架为Hexo_v5.4.0 #徽标提示语
    - link: https://butterfly.js.org/
      shields: https://img.shields.io/badge/Theme-Butterfly-6513df?style=flat&logo=bitdefender
      message: 主题版本Butterfly_v3.8.2
    - link: https://www.jsdelivr.com/
      shields: https://img.shields.io/badge/CDN-jsDelivr-orange?style=flat&logo=jsDelivr
      message: 本站使用JsDelivr为静态资源提供CDN加速
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Vercel-brightgreen?style=flat&logo=Vercel
      message: 本站采用双线部署，默认线路托管于Vercel
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Coding-0cedbe?style=flat&logo=Codio
      message: 本站采用双线部署，联通线路托管于Coding
    - link: https://github.com/
      shields: https://img.shields.io/badge/Source-Github-d021d6?style=flat&logo=GitHub
      message: 本站项目由Github托管
    - link: http://creativecommons.org/licenses/by-nc-sa/4.0/
      shields: https://img.shields.io/badge/Copyright-BY--NC--SA%204.0-d42328?style=flat&logo=Claris
      message: 本站采用知识共享署名-非商业性使用-相同方式共享4.0国际许可协议进行许可
  swiper_css: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.css
  swiper_js: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.js
  swiperbdage_init_js: https://npm.elemecdn.com/hexo-butterfly-footer-beautify/lib/swiperbdage_init.min.js

```

3. 1.3修改

```

//外挂标签，并没有做出修改，但资源已上传b2

# tag-plugins-plus
# see https://akilar.top/posts/615e2dec/
tag_plugins:
  enable: true # 开关
  priority: 5 #过滤器优先权
  issues: false #issues标签依赖注入开关
  link:
    placeholder: /img/link.png #link_card标签默认的图标图片
  CDN:
    anima: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/font-awesome-animation.min.css #动画标签anima的依赖
    jquery: https://npm.elemecdn.com/jquery@latest/dist/jquery.min.js #issues标签依赖
    issues: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/issues.js #issues标签依赖
    iconfont: //at.alicdn.com/t/font_2032782_8d5kxvn09md.js #参看https://akilar.top/posts/d2ebecef/
    carousel: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/carousel-touch.js
    tag_plugins_css: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/tag_plugins.css

//友联样式

# 友链样式，butterfly为默认样式，volantis为站点卡片样式.flexcard为弹性卡片样式
flink_style: flexcard # butterfly | volantis | flexcard

```

4. 1.4修改

```

//引入新的js

bottom:
    - <script src="/js/fixed-pagination.js" async></script>

```
5. 1.5修改

```
//引入新的js
bottom:
    - <script src="/js/sun_moon.js" async></script>

```

## 增加插件

1. 1.1暂无
2. 1.2新增插件
 * 留言板

```
npm install hexo-butterfly-envelope --save

```

 * 页脚电子钟计时(原生)

```
npm install hexo-butterfly-footer-beautify --save

```

3. 1.3新增插件

 * 外挂标签
 
```
npm install hexo-butterfly-tag-plugins-plus --save

```
 * 编译器 [hexo-renderer-kramed](https://www.npmjs.com/package/hexo-renderer-kramed)

```
//卸载hexo自动编译器

npm uninstall hexo-renderer-marked --save

//安装编译器 hexo-renderer-kramed

npm install hexo-renderer-kramed --save

//如果报错请优先执行下面命令

npm install highlight.js

```
# 插件配置文件

1. 留言板配置文件

```

# envelope_comment
# see https://akilar.top/posts/e2d3c450/
envelope_comment:
  enable: true #控制开关
  custom_pic:      
    cover: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/violet.jpg #信笺头部图片
    line: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/line.png #信笺底部图片
    beforeimg: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/before.png # 信封前半部分
    afterimg: https://npm.elemecdn.com/hexo-butterfly-envelope/lib/after.png # 信封后半部分
  message: #信笺正文，多行文本，写法如下
    - 有什么想问的？
    - 有什么想说的？
    - 有什么想吐槽的？
    - 哪怕是有什么想吃的，都可以告诉我哦~
  bottom: 自动书记人偶竭诚为您服务！ #仅支持单行文本
  height: #1050px，信封划出的高度
  path: #【可选】comments 的路径名称。默认为 comments，生成的页面为 comments/index.html
  front_matter: #【可选】comments页面的 front_matter 配置
    title: 留言板
    comments: true

```

2. 页脚电子钟计时(原生)

```
# footer_beautify
# 页脚计时器：[Native JS Timer](https://akilar.top/posts/b941af/)
# 页脚徽标：[Add Github Badge](https://akilar.top/posts/e87ad7f8/)
footer_beautify:
  enable:
    timer: true # 计时器开关
    bdage: true # 徽标开关
  priority: 5 #过滤器优先权
  enable_page: all # 应用页面
  exclude: #屏蔽页面
    # - /posts/
    # - /about/
  layout: # 挂载容器类型
    type: id
    name: footer-wrap
    index: 0
  # 计时器部分配置项
  runtime_js: https://npm.elemecdn.com/hexo-butterfly-footer-beautify@1.0.0/lib/runtime.js
  runtime_css: https://npm.elemecdn.com/hexo-butterfly-footer-beautify@1.0.0/lib/runtime.css
  # 徽标部分配置项
  swiperpara: 3 #若非0，则开启轮播功能，每行徽标个数
  bdageitem:
    - link: https://hexo.io/ #徽标指向网站链接
      shields: https://img.shields.io/badge/Frame-Hexo-blue?style=flat&logo=hexo #徽标API
      message: 博客框架为Hexo_v5.4.0 #徽标提示语
    - link: https://butterfly.js.org/
      shields: https://img.shields.io/badge/Theme-Butterfly-6513df?style=flat&logo=bitdefender
      message: 主题版本Butterfly_v3.8.2
    - link: https://www.jsdelivr.com/
      shields: https://img.shields.io/badge/CDN-jsDelivr-orange?style=flat&logo=jsDelivr
      message: 本站使用JsDelivr为静态资源提供CDN加速
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Vercel-brightgreen?style=flat&logo=Vercel
      message: 本站采用双线部署，默认线路托管于Vercel
    - link: https://vercel.com/
      shields: https://img.shields.io/badge/Hosted-Coding-0cedbe?style=flat&logo=Codio
      message: 本站采用双线部署，联通线路托管于Coding
    - link: https://github.com/
      shields: https://img.shields.io/badge/Source-Github-d021d6?style=flat&logo=GitHub
      message: 本站项目由Github托管
    - link: http://creativecommons.org/licenses/by-nc-sa/4.0/
      shields: https://img.shields.io/badge/Copyright-BY--NC--SA%204.0-d42328?style=flat&logo=Claris
      message: 本站采用知识共享署名-非商业性使用-相同方式共享4.0国际许可协议进行许可
  swiper_css: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.css
  swiper_js: https://npm.elemecdn.com/hexo-butterfly-swiper/lib/swiper.min.js
  swiperbdage_init_js: https://npm.elemecdn.com/hexo-butterfly-footer-beautify/lib/swiperbdage_init.min.js

```
3. [外挂标签][3]

```
# tag-plugins-plus
# see https://akilar.top/posts/615e2dec/
tag_plugins:
  enable: true # 开关
  priority: 5 #过滤器优先权
  issues: false #issues标签依赖注入开关
  link:
    placeholder: /img/link.png #link_card标签默认的图标图片
  CDN:
    anima: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/font-awesome-animation.min.css #动画标签anima的依赖
    jquery: https://npm.elemecdn.com/jquery@latest/dist/jquery.min.js #issues标签依赖
    issues: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/issues.js #issues标签依赖
    iconfont: //at.alicdn.com/t/font_2032782_8d5kxvn09md.js #参看https://akilar.top/posts/d2ebecef/
    carousel: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/assets/carousel-touch.js
    tag_plugins_css: https://npm.elemecdn.com/hexo-butterfly-tag-plugins-plus@latest/lib/tag_plugins.css

```