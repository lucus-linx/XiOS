[Github文档 - SSH](https://docs.github.com/zh/authentication/connecting-to-github-with-ssh/about-ssh)



# 2025实操

## 1. 检查现有的SSH密钥

输入命令以查看是否存在现有的 SSH 密钥：

```sh
$ ls -al ~/.ssh
```



## 2. 生成新密钥

```shell
$ ssh-keygen -t ed25519 -C "lionsom.linx@qq.com"
```



```sh
# 详细过程
# 1.选择一个路径
# 2.输入空密码
~/.ssh  ssh-keygen -t ed25519 -C "lionsom.linx@qq.com"                                                ✔  00:08:55
Generating public/private ed25519 key pair.
Enter file in which to save the key (/Users/linxiang/.ssh/id_ed25519): /Users/linxiang/.ssh/id_ed25519_202508
Enter passphrase for "/Users/linxiang/.ssh/id_ed25519_202508" (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/linxiang/.ssh/id_ed25519_202508
Your public key has been saved in /Users/linxiang/.ssh/id_ed25519_202508.pub
The key fingerprint is:
SHA256:xh9wCsFzQt51m1OtNPAZTs+K90aLvweErvYYvZG+wIU lionsom.linx@qq.com
The key's randomart image is:
+--[ED25519 256]--+
|     oo   . o.+. |
|     .+o.. . Bo=.|
|      o+o . +o+oo|
|       o + ..oo. |
|        S E.o.o .|
|       . o +.ooo.|
|          =.+. oo|
|          o= o...|
|         ...=. oo|
+----[SHA256]-----+

```



## 3. 基础连接测试

```sh
# 连接测试
$ ssh -T git@github.com                                                                              ✔  

git@github.com: Permission denied (publickey).
```

