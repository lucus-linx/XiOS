# 一、GitLab开启双重验证（2FA）

在 GitLab 开启双重验证（2FA）后，已有的仓库需要特别处理，尤其是在推送或拉取时，因为 GitLab 会要求使用专用的身份验证方法来代替原有的密码验证。以下是处理方式：



## 1. 使用个人访问令牌（Personal Access Tokens）

GitLab 在开启双重验证后，不再支持通过用户名和密码进行身份验证。你需要使用个人访问令牌（PAT）来代替密码。

### 步骤：

1. **生成个人访问令牌**：

    - 登录 GitLab。
    - 点击右上角的头像，选择 **Settings**（设置）。
    - 在左侧导航栏中，选择 **Access Tokens**。
    - 输入令牌的名字、选择权限（建议选择 `api` 或 `read_repository`，如果你需要推送代码，则选择 `write_repository`）。
    - 生成令牌后，**务必保存令牌**，因为你将无法再次看到它。

2. **配置 Git**： 在本地使用 Git 操作时，替换掉原本使用用户名和密码的方式，改为使用个人访问令牌：

    - 在进行 `git push` 或 `git pull` 时，GitLab 会要求你输入用户名和密码。
    - 在此处输入你的 GitLab **用户名**，然后在密码字段中使用 **个人访问令牌**（而不是 GitLab 的密码）。

    例如：

    ```bash
    git push https://gitlab.com/username/repository.git
    ```

    当提示输入密码时，输入你生成的 **个人访问令牌**。



## 2. 使用 SSH 密钥（推荐）

另一个推荐的方式是使用 **SSH 密钥**，因为 SSH 不依赖于用户名和密码验证，适合长期使用且更安全。

### 步骤：

1. **生成 SSH 密钥**（如果你还没有）： 打开终端并执行以下命令：

    ```bash
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```

    按照提示完成生成，并保存密钥。

2. **将 SSH 公钥添加到 GitLab**：

    - 登录 GitLab。
    - 进入 **Settings** > **SSH Keys**。
    - 将生成的 `id_rsa.pub` 文件内容粘贴到 **Key** 字段，点击 **Add key**。

3. **配置 Git 使用 SSH**： 将仓库的远程地址更改为 SSH 地址（如果还没有更改）：

    ```bash
    git remote set-url origin git@gitlab.com:username/repository.git
    ```

    然后你就可以使用 `git push`、`git pull` 等命令了，无需每次输入密码或令牌。



## 3. 其他注意事项

- **现有仓库**：已经存在的仓库不需要进行特别的操作，只需要在推送时使用新的身份验证方式即可。
- **CI/CD**：如果你使用 GitLab CI/CD，在 `.gitlab-ci.yml` 文件中配置的 `CI_JOB_TOKEN` 仍然有效，并且 GitLab CI 会自动使用令牌进行身份验证。
- **Token 和 SSH 密钥的选择**：如果你在多个地方（比如多个开发环境）需要操作 GitLab，使用 SSH 密钥会更方便；如果你只在某个地方进行访问，使用个人访问令牌也很方便。

通过这些方法，你可以继续无缝地管理现有的仓库，同时享受 GitLab 双重验证带来的额外安全保障。





# 二、GitLab实操 - SSH

* [Generating a new SSH key pair](http://git.qpaas.com/help/ssh/README#generating-a-new-ssh-key-pair)



## ED25519 SSH keys

```sh
$ ssh-keygen -t ed25519 -C "597207909@qq.com"
$ ssh-keygen -t ed25519 -C "597207909@qq.com" -f ~/.ssh/id_ed25519_gitlab


# 真实
(base) ➜ ~ ssh-keygen -t ed25519 -C "597207909@qq.com" -f ~/.ssh/id_ed25519_gitlab
Generating public/private ed25519 key pair.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/qiyeyun/.ssh/id_ed25519_gitlab
Your public key has been saved in /Users/qiyeyun/.ssh/id_ed25519_gitlab.pub
The key fingerprint is:
SHA256:u59wlonzFouuQy6vVDAx87KGH0WXNcGSIS/FPwYN8Gg 593207939@qq.com
The key's randomart image is:
+--[ED25519 256]--+
|    ooBB=        |
|   + Oo=+.       |
|  . E +o         |
|   * *  +        |
|  o o ..A.       |
|   . ..  o.o     |
|    .o  =.=o     |
|   .. o .Ao.     |
|    .+o+oo+      |
+----[SHA256]-----+
```



## 查看公钥

```sh
$ pbcopy < ~/.ssh/id_ed25519_gitlab.pub

# or

$ cat  ~/.ssh/id_ed25519_gitlab.pub
```



添加 SSH 密钥到 SSH 代理（如果需要）：

```sh
$ ssh-add --apple-use-keychain ~/.ssh/id_ed25519_gitlab
```



## 配置 `~/ssh/config` 文件

```sh
# github
Host github.com
Hostname ssh.github.com
Port 443
AddKeysToAgent yes
UseKeychain yes
IdentityFile ~/.ssh/id_ed25519


# gitlab
Host git.qpaas.com
HostName git.qpaas.com
User git
AddKeysToAgent yes
UseKeychain yes
IdentitiesOnly yes
PreferredAuthentications publickey
IdentityFile ~/.ssh/id_ed25519_gitlab
```



## 验证

```sh
$ ssh -T git.qpaas.com
Welcome to GitLab, @linxiang!
```





# 三、AI - 回复

要配置 SSH 来方便地访问 GitLab，特别是当你有多个 Git 仓库或多个 GitLab 账户时，使用 `~/.ssh/config` 文件可以让你更轻松地管理不同的 SSH 配置。

### 1. **配置 SSH 密钥**

首先，你需要为 GitLab 配置 SSH 密钥。如果还没有生成 SSH 密钥，请按以下步骤操作：

#### 生成 SSH 密钥：

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

然后，按照提示选择保存路径，默认保存到 `~/.ssh/id_rsa`。

#### 添加 SSH 密钥到 SSH 代理（如果需要）：

```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```

#### 将公钥添加到 GitLab：

1. 登录 GitLab。
2. 进入 **Settings** > **SSH Keys**。
3. 打开 `~/.ssh/id_rsa.pub`，复制公钥内容，粘贴到 GitLab 的 SSH Key 输入框中，点击 **Add key**。

### 2. **配置 `~/.ssh/config` 文件**

你可以使用 `~/.ssh/config` 文件为 GitLab 配置特定的 SSH 配置，使得每次与 GitLab 通信时都能自动使用正确的密钥。

#### 编辑 `~/.ssh/config` 文件：

打开 `~/.ssh/config` 文件（如果文件不存在，可以新建）：

```bash
nano ~/.ssh/config
```

然后根据你的需求配置不同的 GitLab 账户或者仓库。例如，如果你有多个 GitLab 账户，可以为每个账户设置不同的配置。

#### 示例 1：为默认 GitLab 账户配置 SSH

如果你只有一个 GitLab 账户，可以简单地配置：

```bash
Host gitlab.com
  User git
  Hostname gitlab.com
  IdentityFile ~/.ssh/id_rsa
  IdentitiesOnly yes
```

- `Host gitlab.com`：指明这个配置是针对 `gitlab.com` 的。
- `User git`：指定使用 `git` 用户进行 SSH 连接。
- `Hostname gitlab.com`：指定 GitLab 的主机名。
- `IdentityFile ~/.ssh/id_rsa`：指定用于 GitLab 的私钥路径。
- `IdentitiesOnly yes`：确保 SSH 只使用指定的密钥进行连接，而不是尝试所有可用的密钥。

#### 示例 2：为多个 GitLab 账户配置 SSH

如果你有多个 GitLab 账户（例如一个用于个人项目，一个用于工作项目），你可以为每个账户设置不同的 SSH 密钥。

```bash
# 工作 GitLab 账户
Host gitlab-work
  User git
  Hostname gitlab.com
  IdentityFile ~/.ssh/id_rsa_work
  IdentitiesOnly yes

# 个人 GitLab 账户
Host gitlab-personal
  User git
  Hostname gitlab.com
  IdentityFile ~/.ssh/id_rsa_personal
  IdentitiesOnly yes
```

在这个例子中，你为工作和个人的 GitLab 配置了不同的 SSH 密钥。

#### 示例 3：配置不同的 GitLab 项目使用不同的密钥

假设你为不同的项目使用不同的密钥，也可以使用类似的配置：

```bash
# 项目1的GitLab
Host gitlab-project1
  User git
  Hostname gitlab.com
  IdentityFile ~/.ssh/id_rsa_project1
  IdentitiesOnly yes

# 项目2的GitLab
Host gitlab-project2
  User git
  Hostname gitlab.com
  IdentityFile ~/.ssh/id_rsa_project2
  IdentitiesOnly yes
```

### 3. **使用配置的 SSH 配置连接 GitLab**

一旦配置好了 `~/.ssh/config`，你就可以使用配置的别名来克隆或操作 GitLab 仓库。

例如，使用 `gitlab-personal` 配置的账户来操作个人仓库：

```bash
git clone git@gitlab-personal:username/repository.git
```

或者，如果是工作仓库：

```bash
git clone git@gitlab-work:username/repository.git
```

Git 会根据 `~/.ssh/config` 文件自动选择正确的密钥进行身份验证。

### 4. **验证配置**

在终端中执行以下命令来验证 SSH 配置是否正确：

```bash
ssh -T git@gitlab.com
```

如果一切配置正确，你应该会看到类似以下的输出：

```bash
Welcome to GitLab, @your-username!
```

如果你配置了多个账户，请使用你在 `~/.ssh/config` 中设置的别名进行验证，例如：

```bash
ssh -T git@gitlab-work
```

### 总结

通过配置 `~/.ssh/config` 文件，你可以为不同的 GitLab 账户或项目使用不同的 SSH 密钥，避免每次输入密码，并简化 Git 操作。使用 SSH 密钥而非用户名和密码，也能提高安全性，特别是在开启 GitLab 双重验证的情况下。