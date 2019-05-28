# 自定义

## 忽略特殊的文件
将一些必须放在git工作目录下并不适合提交的文件忽略。
创建一个`.gitignore`，直接写文件名就可以了。

## 设置别名
如将status设置为st，语句如下。
```
git config --global alias.st status
```
将reset HEAD设置为unstaged，语句如下。
```
git config --global alias.unstage 'reset HEAD'
```
配置Git的时候，加上`--global`是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。
每个仓库的Git配置文件都放在`.git/config`文件中。
别名就在[alias]后面，要删除别名，直接把对应的行删掉即可。
当前用户的Git配置文件放在用户主目录下的一个隐藏文件`.gitconfig`中。
