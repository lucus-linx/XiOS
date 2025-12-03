# Branch

```shell
# 查看本地分支
$ git branch
# 查看远程分支
$ git branch -a

# 删除远程分支
$ git push origin --delete <branchName>
```



# Tag

```shell
# 打tag
$ git tag <tagName>

# 仅仅推送tag
$ git push --tags
# 推送提交以及tag
$ git push origin master --tags

# 查看远程仓库的标签
$ git ls-remote --tags


# 更新远程tag到本地
$ git fetch --tags
$ git fetch origin --tags

# 删除本地tag
$ git tag -d <tagname>

# 删除远程tag
$ git push origin --delete tag <tagName>
$ git push origin :refs/tags/v0.1

# 显示指定tag详细信息
$ git show 
$ git show <tagName>
```



