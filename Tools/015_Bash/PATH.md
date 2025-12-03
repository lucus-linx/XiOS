# 一、SEHLL 类型

## 1.1、查看系统中的shell

```
➜ ~ cat /etc/shells
# List of acceptable shells for chpass(1).
# Ftpd will not allow users to connect who are not using
# one of these shells.

/bin/bash
/bin/csh
/bin/dash
/bin/ksh
/bin/sh
/bin/tcsh
/bin/zsh
```

##1.2、查看默认shell

```
➜  ~ echo $SHELL
/bin/zsh
```

## 1.3、修改系统默认shell

当前默认为zsh，改为bash

```
➜  ~ chsh -s /bin/bash
Changing shell for qiyeyun.
Password for qiyeyun: 
```

**输入密码，重启Terminal，完成。**

## 1.4、切换shell

```
// 默认shell
➜  ~ echo $SHELL
/bin/zsh

// 切换bash
➜  ~ bash
bash-3.2$ 

// 返回默认shell
➜  ~ bash
bash-3.2$ exit
exit
➜  ~ 
```

## 1.5、查看zsh/bash版本

```
➜  ~ zsh --version
zsh 5.3 (x86_64-apple-darwin18.0)
➜  ~ bash -version
GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin18)
Copyright (C) 2007 Free Software Foundation, Inc.
```



# 二、环境变量配置文件

## 2.1、默认Bourne Shell

其环境变量配置文件及加载顺序如下：

```bash
# 系统级别
/etc/profile
/etc/bashrc
/etc/paths 

# 用户级别
~/.bash_profile # macOS
~/.bash_login 
~/.profile 

~/.bashrc # linux

// ========== 说明 ============
其中 /etc/profile /etc/bashrc 和 /etc/paths 是系统级环境变量，对所有用户都有效。但它们的加载时机有所区别：
/etc/profile    全局公有配置，不建议修改，用户登录时候都会加载该文件
/etc/bashrc		全局公有配置，bash shell执行时，不管是何种方式，都会读取此文件
/etc/paths 		全局公有配置，全局配置建议修改该文件，任何用户登陆时都会读取该文件

后面几个是当前用户级的环境变量。macOS 默认用户环境变量配置文件为 ~/.bash_profile，Linux 为 ~/.bashrc。
如果不存在 ~/.bash_profile，则可以自己创建一个 ~/.bash_profile。
如果 ~/.bash_profile 文件存在，则后面的几个文件就会被忽略
如果 ~/.bash_profile 文件不存在，才会以此类推读取后面的文件
```



## 2.2、默认Zsh

如果使用的是 SHELL 类型是 zsh，则还可能存在对应的 /etc/zshrc 和 ~/.zshrc。

* /etc/zshrc ： 任何用户登录 zsh 的时候，都会读取该文件。

* ~/.zshrc ：某个用户登录的时候，会读取其对应的 ~/.zshrc。



# 三、配置环境变量

## 3.1、查看PATH环境变量：

```
➜ ~ echo $PATH
/Library/Java/JavaVirtualMachines/jdk-14.0.1.jdk/Contents/Home/bin:/opt/anaconda3/bin:/opt/local/bin:/opt/local/sbin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Library/Apple/usr/bin:/Applications/Wireshark.app/Contents/MacOS:/Users/qiyeyun/Flutter/flutter/bin::/Users/qiyeyun/.rvm/bin
```



# 【特】若bash_profile不生效？

>  oh-my-zsh的配置文件为`.zshrc`，而默认shell（bash）的配置文件为`.bash_profile` 。

**若bash_profile不生效？**

1. 打开Oh My Zsh的配置文件`.zshrc`（`vi ~/.zshrc`），在其中添加代码：`source ~/.bash_profile`，
2. 终端执行`source ~/.zshrc`即可



# 【特】Java环境变量问题？

【问】：如果我们不配置JAVA环境变量，`java --version`也可以显示出来信息，为什么？

```
【解惑】
使用 which java 查看路径，发现使用的是 /user/bin/java

➜ ~ java --version
java 14.0.1 2020-04-14
Java(TM) SE Runtime Environment (build 14.0.1+7)
Java HotSpot(TM) 64-Bit Server VM (build 14.0.1+7, mixed mode, sharing)

➜ ~ which java
/usr/bin/java

当我们配置JAVA环境变量后，which java 就会显示我们配置的java路径：

➜ ~ java --version
java 14.0.1 2020-04-14
Java(TM) SE Runtime Environment (build 14.0.1+7)
Java HotSpot(TM) 64-Bit Server VM (build 14.0.1+7, mixed mode, sharing)

➜ ~ which java
/Library/Java/JavaVirtualMachines/jdk-14.0.1.jdk/Contents/Home/bin/java
```