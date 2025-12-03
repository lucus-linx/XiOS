# iTerm2

## 快捷键

| 技巧类别         | 核心功能/快捷键               | 简要说明                                           |
| :--------------- | :---------------------------- | :------------------------------------------------- |
| **基础导航**     | `Ctrl + A` / `Ctrl + E`       | 快速跳转到**行首** / **行尾**                      |
|                  | `Ctrl + F` / `Ctrl + B`       | 向前(**F**orward) / 向后(**B**ackward)移动一个字符 |
|                  | `Option + ←` / `Option + →`   | 按**单词**快速移动（需配置）                       |
|                  |                               |                                                    |
| **文本编辑**     | `Ctrl + U` / `Ctrl + K`       | **删除**从光标到行首 / 行尾的内容                  |
|                  | `Ctrl + W`                    | **删除**光标前的一个单词                           |
|                  |                               |                                                    |
| **标签页与窗口** | `Cmd + T` / `Cmd + W`         | **新建** / **关闭**标签页                          |
|                  | `Cmd + D` / `Shift + Cmd + D` | **垂直分屏** / **水平分屏**                        |
|                  | `Cmd + [` / `Cmd + ]`         | 在分屏面板间**切换**                               |
|                  |                               |                                                    |
| **历史与搜索**   | `Cmd + ;`                     | **自动补全**历史命令                               |
|                  | `Cmd + Shift + H`             | 呼出**剪贴板历史**                                 |
|                  | `Ctrl + R`                    | **搜索**命令历史                                   |
|                  |                               |                                                    |
| **实用功能**     | `Option + Cmd + B`            | **即时回放**，回溯终端输出历史                     |
|                  | `Cmd + /`                     | **高亮显示**当前光标所在位置                       |
|                  |                               |                                                    |



## 个性化配置

1.  **开启无限滚动缓冲区**
    默认情况下，终端能回滚的历史行数有限。勾选 `Preferences > Profiles > Terminal` 中的 **Unlimited scrollback**，可以保留所有历史输出，方便查阅。

2.  **设置热点键，快速呼出/隐藏终端**
    你可以设置一个全局快捷键，让 iTerm2 像“鬼魂”一样随时出现或消失。在 `Preferences > Keys` 中设置一个 **Hotkey**（如 `F12`），之后无论你在什么应用中，按这个键就能调出或隐藏 iTerm2 窗口。

    ![](images/001.png)
    
3. **光标跟随鼠标（Focus follows mouse）**
    如果你习惯让鼠标悬停的窗口自动获得焦点，可以在 `Preferences > Pointer` 中勾选 **Focus follows mouse**。

4. **让 `Option + 方向键` 按单词移动**
    这是 Mac 自带终端的默认行为，但 iTerm2 需要手动设置。最快的方法是：进入 `Preferences > Profiles > Keys`，点击 **Presets** 下拉菜单，选择 **Natural Text Editing** 预设。如果想手动设置，可将 `Option + ←` 映射为发送 Escape 序列 `b`，将 `Option + →` 映射为发送 Escape 序列 `f`。



## 高级应用场景

1.  **配置 SSH 一键登录服务器**
    对于需要频繁登录的远程服务器，可以配置 Profile 实现一键登录，免去重复输入 IP、用户名和密码的麻烦。
    *   **方法一：使用 Expect 脚本**。创建一个脚本文件，然后在 `Profiles` 的 `General` 设置中，在 "Send text at start" 字段调用该脚本。
    *   **方法二：使用 Trigger（触发器）**。在 `Profiles > Advanced > Triggers` 中添加规则，例如当检测到 "password:" 提示时自动发送密码。这种方法更灵活。

2.  **开启 SSH 密钥转发（Agent Forwarding）**
    当需要通过跳板机登录内网服务器时，需要启用 SSH 代理转发。可以在创建 Profile 时，在 "Command" 字段使用 `ssh -A username@jump_host` 命令（`-A` 参数即开启转发）。

