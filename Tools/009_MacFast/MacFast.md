# 零、包管理工具

包管理器又称软件包管理系统，它是在电脑中安装、配置、卸载、升级，有时还包含搜索、发布的工具组合。

**Homebrew**是一款Mac OS平台下的包管理器，拥有安装、卸载、更新、查看、搜索等很多实用的功能。

**apt-get**和**yum**跟Homebrew类似，只不过他们适用的平台是Linux，二者一般会被分别安装到Debian、Ubuntu和RedHat、CentOS中。

软件包管理器，适用于特定开发语言，这类软件包本身的安装需要依赖特定语言环境。

**NPM**（node package manager)，通常称为node包管理器，主要功能就是管理node包，使用Node.js开发的多数主流软件都可以通过npm下载。

**RubyGems**是Ruby的一个包管理器，提供了分发Ruby程序和库的标准格式“gem”，旨在方便地管理gem安装的工具，以及用于分发gem的服务器。使用Ruby开发的软件一般都通过gem进行管理。

**pip** 是通用的 Python 包管理工具，python3对应的是pip3。使用Python开发的软件多使用pip进行管理。



# 一、Homebrew

> Homebrew是Mac OS 不可或缺的套件管理器。

* [Homebrew 官网](https://brew.sh/)



## 1、brew 与 brew cask 区别

> HomeBrew是通过源码的方式来安装软件，但是有时候我们安装的软件是GUI程序应用宝(.dmg/.pkg)，这个时候我们就不能使用HomeBrew了。所以有了HomeBrew Cask的出现
>
> brew cask 是在brew 的基础上一个增强的工具，用来安装Mac上的Gui程序应用包（.dmg/.pkg）, 比如qq、chrome等。它先下载解压到统一的目录中（/opt/homebrew-cask/Caskroom），省掉了自己去下载、解压、拖拽（安装）等步骤，同样，卸载相当容易与干净。然后再软链到~/Applications/目录下, 非常方便，而且还包含很多在 AppStore 里没有的常用软件。

* brew cask的官网是：[caskroom.io](http://caskroom.io)

* github地址是：[https://github.com/Homebrew/homebrew-cask](https://github.com/caskroom/homebrew-cask)



## 2、常用命令

```
➜ ~ which brew			// 展示brew的位置
/usr/local/bin/brew

➜ ~ brew search 										// 列出brew支持的软件
➜ ~ brew search <package_name>      // 搜索

➜ ~ brew install <package_name>     // 安装软件
➜ ~ brew uninstall <package_name>   //  卸载软件

➜ ~ brew list							 // 查看你安装过的包列表
➜ ~ brew list --versions   // 查看你安装过的包列表（包括版本号）

➜ ~ brew update                     // 从服务器上拉取，并更新本地 brew 的包目录
➜ ~ brew upgrade <package_name>     // 更新软件
➜ ~ brew outdated                   // 查看你的软件中哪些有新版本可用
➜ ~ brew cleanup                    // 清理老版本
```



# 二、终端工具

## 1、unrar

> 解压

```
➜ ~ brew install unrar  // 安装

➜ ~ unrar x test.rar		// 解压text.rar文件到当前目录
```



## 2、guetzli

> 图片压缩

* [GitHub - guetzli](https://github.com/google/guetzli)

```
➜ ~ brew install guetzli		// 安装，自动安装依赖Installing guetzli dependency: libpng

// 使用
➜ ~ guetzli [--quality Q] [--verbose] original.png output.jpg
➜ ~ guetzli [--quality Q] [--verbose] original.jpg output.jpg
// 实战
➜ ~ guetzli --quality 85 --verbose 005.png 010.png

// 说明
--quality	指的是质量，取值100~85，默认为95。
--verbose	加此参数后 在执行压缩时会在控制台输出过程。
original.jpg	输入的图片路径
output.jpg	输出的图片路径
```



## 3、CheatSheet

> 显示快捷键，默认按command。

```
➜ ~ brew cask install cheatsheet
```



## 4、Alfred

> Mac 用户不用鼠标键盘的必备神器，配合大量 Workflows，习惯之后可以大大减少操作时间。

* [教程 - 5分钟上手Mac效率神器Alfred以及Alfred常用操作](https://www.jianshu.com/p/e9f3352c785f)



## 5、lastpass-cli

> LastPass 是管理密码的工具，支持二次验证。它提供 命令行 的版本，可以直接通过 brew 安装。
>
> lastpass-cli 是LastPass的命令行版本。

* [GitHub - lastpass-cli](https://github.com/lastpass/lastpass-cli)

```
➜ ~ brew install lastpass-cli		// 安装

➜ ~ lpass help			// 获取帮助

➜ ~ lpass login lionsom.linx@gmail.com		// 登录

➜ ~ lpass show XXX 	// 显示密码记录的详情
```



## 6、oh-my-zsh

> 它是Shell，代替原生bash
>
> 详情请看文档：《Zsh.md》



## 7、zsh-git快捷键

> git是Zsh的插件，就是git命令行的快捷键。
>
> gl  === git pull
>
> gp  ===  git push



## 8、zsh-autosuggestions

> autosuggestions是Zsh的插件，自动补全，详情请查看《Zsh.md》



## 9、autojump

xxx





# 三、工具安装（包含破解）

## 1、MySQL

* [MySQL官网下载：https://dev.mysql.com/downloads/](https://dev.mysql.com/downloads/)

* 教程：[【MySQL安装（Mac版）】](https://juejin.im/post/5cc2a52ce51d456e7079f27f)

> 本地MySQL
>
> 账户：Root
>
> 密码：12345678



## 2、Navicat Premium

> Navicat Premium是一款可视化数据库管理软件。

* [Navicat Premium官网下载：https://www.navicat.com/en/products](https://www.navicat.com/en/products)

* [吾爱破解 - Navicat Premium 12.0.24 for mac已破解](https://www.52pojie.cn/thread-727433-1-1.html)



## 3、Dash

> Dash是一个API文档浏览器和代码片段管理器。

* [Dash User Guide](https://kapeli.com/dash_guide)



## 4、Typora

> Typora是一款MarkDown编辑器。



## 5、Mounty for NTFS（推荐）

* [Mounty for NTFS](https://mounty.app)



## 6、Lookin

> Lookin：免费好用的 iOS UI 调试软件。

* [Lookin](https://lookin.work/)



## 7、LICEcap || GIPHY Capture

> LICEcap || GIPHY Capture 是一款Mac gif录屏软件。

* [LICEcap](https://www.cockos.com/licecap/)

* [GIPHY Capture](https://giphy.com/apps/giphycapture) install in AppStore



## 8、iTerm2

> iTerm2是一款终端。

* [iTerm2](https://www.iterm2.com/)



## 9、Beyond Compare

* [Beyond Compare Download](https://www.scootersoftware.com/download.php)
* [Beyond Compare for Mac 无限试用方法](https://www.seidea.com/2017/03/23/beyond-compare-for-mac-无限试用方法/)

### 9.1、破解原理

> `BCompare` 是应用程序启动的程序，只要在在启动的时候**删除 registry.dat**(`Library/Application Support/Beyond Compare/registry.dat`)注册信息就好了。


* #### registry.dat所在目录：`Library/Application Support/Beyond Compare`

  ![](media_MacFast/001.jpeg)


* #### 移除 registry.dat：`rm registry.dat`

  ![](media_MacFast/002.jpeg)

* #### 重启程序即可



## 10、XMind

[吾爱破解 - 思维导图 Xmind Zen](https://www.52pojie.cn/thread-1064432-1-1.html)



## 11、IntelliJ IDEA

[IntelliJ IDEA 官网](https://www.jetbrains.com/idea/)  

[免费激活参考](https://www.exception.site/essay/how-to-free-use-intellij-idea-2019-3)



## 12、Xnip

可滚动截图



## 13、超级右键



## 14、CleanMyMac







# 四、Chrome插件

[谷粒-Chrome插件英雄榜 ChromeAppHeroes](https://github.com/zhaoolee/ChromeAppHeroes)

[你极力推荐的 Chrome 扩展有哪些？ - 知乎](https://www.zhihu.com/roundtable/mycollegestyle)





## 基础功能增强



### Infinity New Tab



### Online Download Manager



### Imagus



### Search by Image



### FireShot



### OneTab Plus



### ImageAssitant



### Super History Cleaner



### AD Block



### 书签侧边栏







## 学习效率



## 黑科技



## 生活娱乐





##1、OneTap

标签管理插件，节省高达95％的内存，并减轻标签页混乱现象。



## 2、沙拉查词-聚合词典划词翻译

Chrome翻译插件，超级方便。



## 3、LanguageTool

检测输入单词、语法是否错误。



## 4、Chrome清理大师

一键清理您的浏览器缓存和垃圾，保护您的隐私，并使您的浏览器更快。



## 5、JSON-handle

Json工具



## 6、AdGuard

广告拦截器



## 7、LastPass

密码管理



## 8、SimpleUndoClose

这个简单的弹出可让您轻而易举的撤销关闭的标签！



## 9、Vimium



## 10、Absolute Enable Right Click & Copy





# 五、GitHub工具

[让你纵横 GitHub 的五大神器](https://mp.weixin.qq.com/s/NCNcf2RS0c6Gjp0kMwjo_w)

## 1、Octotree

目录一览



## 2、Sourcegraph

快速查看资源



## 3、Enhanced GitHub

下载指定文件



## 4、GitHub Dark Theme

暗黑





# 六、清理Mac

* 缓存
    * `~/资源库/Caches`

* 来自iOS的备份数据 - [官网](https://support.apple.com/zh-cn/HT204215)
    * `~/资源库/Application Support/MobileSync/Backup`
