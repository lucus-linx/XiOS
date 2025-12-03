# VSCode使用

* [官方文档](https://code.visualstudio.com/docs)

- [VS Code 中文社区](https://github.com/vscodecc/vscodecc) 

- [知乎专栏](https://zhuanlan.zhihu.com/vs-code) - Visual Studio Code的最新资讯，热门文章，使用技巧，插件推荐，插件开发攻略等，全部都可以在这里找到。带你玩转VSCode！
- [《Visual Studio Code 权威指南》](https://union-click.jd.com/jdc?e=jdext-1261348777639735296-0&p=AyIGZRhbHQsWAVIaXxEyEgRdG1sRBxU3EUQDS10iXhBeGlcJDBkNXg9JHUlSSkkFSRwSBF0bWxEHFRgMXgdIMkRxFAUJD1RQZT0cBnwKDE4%2BaDpgB2ILWStbHAIQD1QaWxIBIgdUGlsRBxEEUxprJQIXNwd1g6O0yqLkB4%2B%2FjcePwitaJQIWD1cfWhwKGwVSG1wlAhoDZc31gdeauIyr%2FsOovNLYq46cqca50ytrJQEiXABPElAeEgRSG1kQCxQBUxxZHQQQA1YTXAkDIgdUGlscChECXRs1FGwSD1UbWRALFwRWK1slASJZOxoLRlUXU1NONU9QEkdXWRlJbBUDVB9TFgAVN1caWhcA)



# 插件推荐

## HTML相关插件

### 汉化

Chinese (Simplified) (简体中文) Language Pack for Visual Studio Code



### 预览html

open in browser







## 语言支持

首先当然是一些语言支持的插件，这个大家根据自己的需要安装就好了。平时编写什么语言，就安装什么语言的插件。

老梁这里简单列举一下老梁安装过的语言。

### C/C++

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OWhlQic1cFn1cl1esGGPd5vQI2LbSvvfuuoDUtzU5pmlTw5tkeM3Z5wA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

提供C++语法识别、智能补全、代码跳转、调用依赖识别等，一般来说学生党安装这一个就可以了。还有一些其他的插件也非常不错，如C++ Intellisense, C/C++ Clang Command Adapter等。

### Java

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OiamLzowM1NElCMBFjzGJNTCqpL3CmuJ2nhffIxVfdY0Iy6qib6X3dQyQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

提供代码调整、自动补全、jdk 文档查询、Lint、类型检查、debug等功能。虽然老梁安装了这个插件，但实话说老梁一般不在vscode里写Java。

因为Java的工程往往比较庞大，而vscode相对比较轻量级，相对来说不是非常合适。而且Java工程需要的插件也非常多，比如Tomcat、spring、数据库等等……全部安装下来还是比较重的。所以还不如直接使用全部环境都集成好的IDEA。

### Go

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9ORgwHNYCv6LsGEPib4F6TLwSMyOJXDVoLRc56ibTmYkNOw5FGZ5pf1f6g/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

vscode对go语言的支持非常不错，在某些功能上甚至比Jetbrains家的Goland还要好用，比如golint。

和Java一样，golang一般也是用来编写大型的后端项目，这类的项目代码文件非常多，老梁个人感觉还是不太适合vscode。还是更喜欢goland一些， 不过也有很多同事是vscode铁忠粉，坚定使用vscode，所以关于这点仁者见仁。

### Hive SQL

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OCRiaM87mgjth9k1cQO2Q8O02zeQiaTv1PEEXl9Cp5bURHQhzY8sB7TcQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

Hive SQL语法支持，主要就用到高亮和补全，毕竟hive sql都不在本地运行。

### HTML/CSS

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OrSX0K95UCBl5aYKLPmKho86nZlp9VkvX0PibiaF9dC6QAUJa4fpzJZtQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

HTML/CSS语法支持，前端党必备。

### Markdown

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OWDk9ftVVfCJmb5kAC1wsdiav5yY9hwPFlu071icgJlrI0B1pTTgXXzWA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

markdown语法支持，可以在vscode当中编辑markdown文档，还支持图床的图片上传功能。但老梁个人还是更喜欢Typora，很少在vscode当中写文档。

但是由于很多github的repo都提供了markdown语法格式的readme文件，所以还是需要安装一下，这样才方便阅读。

### Python

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OpGB24FHd2FYWwPNRupCcic0uXjoQ6tq7xiajjxunYEeWvXQ9GwicAiaiclw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

Python的语法支持，支持Python的单测、lint、语法高亮、代码格式化、debug、jupyter等功能。

当中老梁最喜欢的是对jupyter的支持，可以在vscode当中快速打开、运行.ipynb文件，再也不用在web当中运行notebook了，体验大大提升。

老梁平时用vscode写Python比较多，因为老梁一般写的Python都是一些插件、工具或者是模型的代码，基本上都是单一的Python文件，而不是大型的工程，所以感觉vscode还是非常好用的。同样，如果是编写大型工程的话，还是感觉Pycharm可能更适合一些。

## 各种神器

上面介绍的都是语言支持型插件，大家根据自己平时编写的需要酌情安装即可。当然这里老梁列举的也是老梁自己安装过的，还有很多其他的语言老梁也没接触过，也就没办法给大家介绍了。

下面来介绍一下功能性的插件，可以实现一些各种各样的功能，有些是开发神器，有些是摸鱼神器，各有各的用处。

### Auto Close Tag

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9ODiby3LiaXv0t87gSibWc4VDbh6LlUiaa9HWNf9HAvias7OOSq8hs43UtSZw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

前端神器，只需要编写左标签，例如`<a>,<body>,<html>`等，会自动替我们完成右侧标签的填充如：`</a>, </body>, </html>`等。

### Auto Rename Tag

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9O0fmWwUEKtgYa2EcDMDial1EXZuwIRd9g2dibpteq7sj6Zqvia8bBw62hA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

前端神器，自动修改标签名，当我们修改一个标签时，自动修改对应的右侧标签。

### Better Comments

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OJmeL9qNDstPoghxadCdUFmaFgnQM6rDibKWHiap9n6tDs8NRzqjbtsbA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

美化注释，可以将我们的多行注释按照类别自动高亮，如：

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OmynHTv42HEWic3hF3VtvINaJjA5NiaRGl4vwbI4MzrBq2icHicCKE5R4OQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

### Bracket Pair Colorizer

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OgapjXsnzMUQBQYgR7k7pw4o04yZjYkicdpic05FRG00uhMSTXzmeRbtQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

开发神器，当使用多层括号嵌套时，自动将不同层次的括号设置成不同的颜色，防止配对时眼瞎。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OJprXtu3zr1AvSX14AmFugB2NqggDMLNwOGeLibRepbe6o0HEzVSd7lQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

### CodeIf

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9O0yRTHBEZPedWuzlabXMDeiar5XIwlIVCbLk7sUibUiaoUuzS7dBGqP2gA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

变量起名神器，还在为起变量名发愁吗？使用它搜索一下，自动推荐合适的变量名，支持中文！

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OaMa5AvvOHC9fWLCxqOtKE20G9DJvMibPeiacXAicdMyicTs4q76ibaJalFQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

### Excel Viewer

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9O3UEibjZaRFCmEnRdcH3KpgSM4KyJjFzry1JQQ6DYLO7IEL7FibALG6JA/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

顾名思义，Excel表格预览，数据分析党的神器，再也不用一个窗口看数据一个窗口写代码了。

### ESLint

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9ODr7mUQzv10kwn5vKqE0RUxrsnibTu8HmLZMwUVaDk4sjyqrZYwKMCWg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

前端神器，不解释。

### Jslint

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9Oj9zQrLr5XsANJxsPW00TmFrF9CXeOwAr40nibSNalqKSA21RyVB8Egg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

JSLint，JavaScript lint工具，前端党必备。

### jupyter

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OMvreCuu0uC1icib4WF66tTUxFHATvIvHwhPS4REjnV1aM97WcZUYUo2w/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

vscode中支持jupyter，和Python插件对jupyter的支持类似。

### leetcode

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OuwgfZH5Rdh99ONaibhW9aqCtBxf1JL3qWKOU7Apyy1kORmMq7Rb7jZg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

上班摸鱼、实验室摸鱼神器，再也不用担心刷题被老板看到了。

### live server

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OGJLhEK7QpUIBu7TDPUOXicAqBDicQAiavvuM8OPyaTBXQ93wNoDYbHKKg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

前端神器，可以在vscode中预览编写的网页。

### Path Intellisense

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OziagCknJK4XYeDzaWiacXpfFplaBk4lFTyfEQOQVL6FYoRre1jicFtmxw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

编码神器，相对路径自动补全

### Remote - SSH

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OFhSTD90xIqlhzGUicVaTLIloYUSX18S5hQRIxZ8kXJscUVcCjfcQEVw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

开发神器，通过vscode以窗口的形式连接远程服务器，直接在vscode当中编写服务器代码！

### Tabnine

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9O3txlxgzCoC3hOWXBZGfOjgRpLm9JQVvny2bZ9mR5uNP5FWj8sFOHJQ/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

开发神器，超强大的代码自动补全。

### Terminal Here

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9ObYzM4e6PsFPZShAF5CjXs49eh8gPy4bTBqB7JOmw7xqAcT7TEbIVzw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

开发神器，在当前窗口打开terminal，再也不用每次开terminal都要不停地cd了。

### vscode-icons

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OImGL88ZnEGjSMLJZtSic6icR6eIpOcLicd5yKyvdicpljGme9vPpwFphvg/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

给你的vscode中文件夹、文件换上更好看的图标。

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OoYibcuIw8JDeahAcEuNCYRVPNEMR9RPVJfPuW4Ua7W58gA20JkZZcfw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

### zhihu

![图片](https://mmbiz.qpic.cn/mmbiz_jpg/6nNCNSoRubxGpmJ6hyGvI8qQKBS6DP9OuJLs8xs3Sl1TaFJVwG4GSjMiaeRZKkcEzpFvB47ogdZGQiaQMyzUibTOw/640?wx_fmt=jpeg&tp=webp&wxfrom=5&wx_lazy=1&wx_co=1)

摸鱼神器，年薪百万的秘密……

vscode当中好用的插件还有非常多，如果还知道什么其他神器的，不妨在下方留言分享给大家吧~

