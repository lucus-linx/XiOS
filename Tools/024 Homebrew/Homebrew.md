* [Homebrew](https://brew.sh/)

* [程序员 Homebrew 使用指北](https://sspai.com/post/56009#toc_0)



# 一、Homebrew相关命令

## 1. Install Homebrew

```sh
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```



## 2. 查看Homebrew版本

```sh
$ brew --version                                                                           
# or
$ brew -v
```



## 3. 检查 Hombrew 环境

如果你的 Hombrew 没有办法正常的工作，你可以执行 `brew doctor` 来开启 Homebrew 自带的检查，从而确认有哪些问题，并进行修复。

```sh
$ brew doctor
```



## 4. 更新Hombrew

Homebrew 经常会在执行命令的时候触发更新，不过如果你想要主动检查更新，可以执行 `brew update` 来唤起 Homebrew 的更新。

```sh
$ brew update
```



## 5. 配置环境变量

如果出现如下问题，则需要配置环境变量。

```bash
$ brew -v
brew：command not found
```

执行 `which $SHELL` 确认你的 macOS 的默认 Shell 是哪个？

```sh
$ which $SHELL
```

通常是 `zsh` 或 `bash`，对应的配置文件为 `~/.zshrc` 或 `~/.bash_profile`。

```bash
# 添加环境变量至 .zshrc
$ echo 'export PATH="/usr/local/bin:/usr/local/sbin:/opt/homebrew/bin:/opt/homebrew/sbin:$PATH"' >> ~/.zshrc

# 刷新环境变量
$ source ~/.zshrc
```

完了之后，再执行 `brew -v` 应该就能正常输出版本号了。



## 6. Homebrew 源切换

可以考虑切换为国内的镜像源，比如：

- [清华大学镜像源](https://link.zhihu.com/?target=https%3A//mirrors.tuna.tsinghua.edu.cn/help/homebrew/)
- [中国科学技术大学镜像源](https://link.zhihu.com/?target=http%3A//mirrors.ustc.edu.cn/help/brew.git.html)

如果使用 4.x 最新的 JSON API 安装方式（推荐），添加以下环境变量配置：

```sh
echo '
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.ustc.edu.cn/brew.git"
export HOMEBREW_API_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles/api"
export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.ustc.edu.cn/homebrew-bottles/bottles"
' >> ~/.zshrc
```

> 若要重置为官方镜像源，移除以上环境变量即可。



## 7. 关闭收集匿名数据

如不希望 Homebrew 收集匿名数据，可以通过设置环境变量关闭：

```bash
echo 'export HOMEBREW_NO_ANALYTICS=1' >> ~/.zshrc
```



## 8. Homebrew 自动更新

默认情况下，在执行 `brew install`、`brew upgrade`、`brew tap` 之前，每隔第一段时间会自动执行 `brew update` 以获取最新的 Homebrew 版本。

在 4.0 起自动执行频率为 `24h`，如果开启了 `HOMEBREW_NO_INSTALL_FROM_API=1` 频率为 `5min`。可通过以下环境变量完全禁用、设置时间间隔。

```bash
echo '
export HOMEBREW_NO_AUTO_UPDATE=1
export HOMEBREW_AUTO_UPDATE_SECS=86400
' >> ~/.zshrc
```

这就是每次安装/更新包时，先出现 `Downloading https://formulae.brew.sh/api/formula.jws.json` 的原因。这个 JSON 文件有 4M 多，如果加上默认的镜像源，不慢才怪。



# 二、Homebrew 相关路径

```sh
# 
$ where brew
$ which brew

# 显示 Homebrew 本地的 Git 仓库
$ brew --repo

# 显示 Homebrew 安装路径
$ brew --prefix

# 显示 Homebrew Cellar 路径
$ brew --cellar

# 显示 Homebrew Caskroom 路径
$ brew --caskroom

# 缓存路径
$ brew --cache
```

Homebrew 默认安装路径如下：

- macOS ARM: `/opt/homebrew`
- macOS Intel: `/usr/local`

以 `brew install git` 为例：

> 1. Homebrew 将 git 下载至 `/usr/local/Cellar/git/<version>/` 目录下，其二进制文件在 `/usr/local/Cellar/git/<version>/bin/git`。
> 2. Homebrew 为 `/usr/local/Cellar/git/<version>/bin/git` 创建了一个软链文件至 `/usr/local/bin` 里。



> macOS ARM 的路径对应是：
> `/opt/homebrew/Cellar/git/<version>/`
> `/opt/homebrew/Cellar/git/<version>/bin/git`
> `/opt/homebrew/bin`。
> 这也是 macOS ARM 要将 `/opt/homebrew/bin` 添加到 `PATH` 环境变量的原因。



当执行 `brew uninstall` 时，会将 `/usr/local/Cellar` 下对应包目录删除，对应的链接关系也会移除。 当执行 `brew cleanup` 时，会将 `/usr/local/Cellar` 所有包里的旧版本，只保留最新版本。





# 三、命令行工具、GUI 应用

- **Formulae**：一般是那些命令行工具、开发库、字体、插件等不含 GUI 界面的软件。
- **Casks**：是指那些含有 GUI 图形化界面的软件，比如 Chrome、FireFox 等。



如安装的是 GUI 应用，加上 `--cask` 参数。比如 `brew install docker --cask`。
如需强制卸载，加上 `--force` 参数。

```sh
$ brew search google
==> Formulae
aws-google-auth                      google-benchmark
google-java-format                   google-sql-tool                      goose
google-authenticator-libpam          google-go
google-sparsehash                    googletest

==> Casks
google-ads-editor                             google-chrome
google-drive                                  google-web-designer
google-analytics-opt-out                      google-chrome@beta                            google-earth-pro                              googleappengine
google-assistant                              google-chrome@canary                          google-japanese-ime                           marshallofsound-google-play-music-player
google-chat                                   google-chrome@dev
google-japanese-ime@dev                       moefe-google-translate
google-chat-electron                          google-cloud-sdk                              google-trends                                 vpn-by-google-one
```



# 四、软件管理相关命令

## 1. 安装、卸载、重装

```sh
# 安装
$ brew install [软件名]

# 卸载
$ brew uninstall [软件名]

# 重装
$ brew reinstall [软件名]
```



## 2. 搜索

```sh
$ brew search [关键词]
```



## 3. 查看已经安装的包

```sh
$ brew list                     # 所有的软件，包括 Formulae  和 Cask
$ brew list --formulae          # 所有已安装的 Formulae
$ brew list --cask              # 所有已安装的 Casks
$ brew list <package-name>      # 列举某个 Formulate 或 Cask 的详细路径
```



## 4. 更新

```sh
# 查看所有有更新版本的软件
$ brew outdated

# 更新单个软件
$ brew upgrade [软件名]

# 更新所有软件
$ brew upgrade
```



### a. 锁定某个不想更新的包

```sh
$ brew pin <package-name>       # 锁定指定包
$ brew unpin <package-name>     # 取消锁定指定包
```



## 5. 查看包的信息

```sh
# 显示某个包信息
$ brew info [软件名] 

# 显示安装的软件数量、文件数量以及占用空间
$ brew info
```



## 6. 清理软件的旧版

```sh
# 清理特定软件的旧版
$ brew cleanup [软件名]

# 清理系统中所有软件的历史版本
$ brew cleanup

# 查看可清理的旧版本包
$ brew cleanup -n
```



## 7. 卸载某个已经安装的包

```sh
$ brew uninstall [软件名]
```





# 五、管理后台软件相关命令

- `brew services list`： 查看所有服务
- `brew services run [服务名]`: 单次运行某个服务
- `brew services start [服务名]`: 运行某个服务，并设置开机自动运行。
- `brew services stop [服务名]`：停止某个服务
- `brew services restart`：重启某个服务。
