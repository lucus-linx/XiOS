[阮一峰 — Vim 配置入门](http://www.ruanyifeng.com/blog/2018/09/vimrc.html)

[Vim插件管理工具 — Vundle](https://github.com/VundleVim/Vundle.vim)



# 一、Vim配置文件

Vim 的全局配置一般在 `/etc/vim/vimrc` 或者 `/etc/vimrc`，对所有用户生效。

用户个人的配置在 `~/.vimrc`。

如果只对单次编辑启用某个配置项，可以在命令模式下，先输入一个冒号，再输入配置。如：`:set number`

查询某个配置项是打开还是关闭，可以在命令模式下，输入该配置，并在后面加上问号。

如：`:set number?`，上面的命令会返回`number`或者`nonumber`。



# 二、个人配置Vim

```shell
# 创建 ~/.vimrc
➜ ~ touch .vimrc

# 查看目录包括隐藏文件
➜ ~ ls -a

# vim编辑.vimrc
➜ ~ vim .vimrc
-----------------
# 添加行显示配置
set number
# 保存
:wq
-----------------

# 打开vim编辑 显示行
➜ ~ vim 001.c
```



# 三、常用基本配置

```shell
"显示行号
set number

"语法高亮
syntax on

"显示标尺
set ruler

"自动折行
set wrap                      

"制表符为4 
set tabstop=4 

"设置tab符自动转换为空格
set expandtab

"设置智能缩进，其他可选缩进方式：autoindent / cindent / indentexpr
 set smartindent
 
 "设置配色方案，预设主题有：default、desert、darkblue等
 colorscheme default
 
 
......
```



# 四、Vim插件管理

[Vim插件管理工具 — Vundle](https://github.com/VundleVim/Vundle.vim)

























