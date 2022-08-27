---
title: 友情链接
date: 2022-08-15 05:40:14
type: "link"
---

{% folding 我的友联 %}

{% tabs test1 %}
<!-- tab 🦋butterfly-🍭candy -->
```YML
- name: 花语阁
  link: https://www.pigax.cn/
  avatar: https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/5c52d93f4a509998e48da1b6ef734371.png
  descr: 花语倾城 江无月
  siteshot: https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi@1.0.2/IMG_20220618_111643.jpg
```
<!-- endtab -->

<!-- tab 🍬Volantis -->
```JSON
{
"title": "花语阁",
"screenshot": "https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi@1.0.2/IMG_20220618_111643.jpg",
"url": "https://www.pigax.cn/",
"avatar": "https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/5c52d93f4a509998e48da1b6ef734371.png",
"description": "花语倾城 江无月",
"keywords": "花语阁"
}
```
<!-- endtab -->

<!-- tab 🍫General -->
|  名称   | 数值  |
|  ----  | ----  |
| 站点名称  | 花语阁 |
| 站点截图  | https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi@1.0.2/IMG_20220618_111643.jpg |
| 站点链接 | https://www.pigax.cn/ |
| 站长头像 | https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/5c52d93f4a509998e48da1b6ef734371.png |
| 站点描述 | 花语倾城 江无月 |
| 站点关键词 | 花语阁 |
<!-- endtab -->
{% endtabs %}

{% endfolding %}

{% folding 友联示例 %}

参照以下格式留言即可。

```YML
- name:       #站点名称
  link:       #站点链接
  avatar:     #站长头像
  descr:      #站点描述
  siteshot:   #站点截图
```
示例：

```YML
- name: 花语阁
  link: https://www.pigax.cn/
  avatar: https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi/5c52d93f4a509998e48da1b6ef734371.png
  descr: 花语倾城 江无月
  siteshot: https://npm.elemecdn.com/butterfly-footer-beautify-ruoxi@1.0.2/IMG_20220618_111643.jpg
```
{% tip warning faa-horizontal animated faa-fast %}
站点截图建议自己提供，尺寸尽量不要大于300*300。
未提供站点预览图的，本站会根据贵站链接调用以下API自动获取贵站的站点截图。
对于做了反扒措施的站点，API获取的将是反扒页面，望知悉。
{% endtip %}

```MARKDOWN
https://image.thum.io/get/width/400/crop/800/allowJPG/wait/20/noanimate/https://<你的域名>/
```

{% endfolding %}
