# Git基础

## 第一次提交

### 初始化
初始化的过程是在自己的项目文件夹中使用命令新建一个`.git`的文件夹，如下所示，这样就生成了一个空的版本库。
```
git init
```
此后可以使用以下的语句将文件提交到版本库的暂存区。（该操作后面可以跟随多个文件）
```
git add <filename>
```
### 提交至仓库
要将文件从暂存区提交到仓库首次使用的时候需要设置邮箱和用户名。
```
git config --global user.email ""
git config --global user.name ""
```
然后用下面的语句将其提交，其中`-m`后的字符串是`commit`自行设定的记录信息。
```
git commit -m "first commit"
```



## 修改的文件

### 查看被修改文件

可以用以下的语句查看哪些文件在工作区和版本库中不同。

```
git status
```
总体来说有以下的三种情况：

- 未add的文件：显示为Untracked files
- add但未commit的文件：显示为Changes not staged for commit（处于暂存区中，属于版本库）
- commit后：显示为nothing to commit, working tree clean（进入分支，也属于版本库）

### 查看修改处

```
git diff
```
只查看单个文件区别
```
git diff HEAD -- <filename>
```

**注意**
如果有文件处于版本库，但是又在工作区中被修改，有两种情况。

修改是有必要的：需要重新add。
进行了错误的修改：可以用以下语句回到最后一次`commit`或`add`的状态。

```
git checkout -- file
```
如果已经进行了`add`操作，可以用以下语句让暂存区和分支一样，再用上面一条命令改工作区。
```
git reset HEAD file
```



## 版本回退

### 查看版本日记

```
git log
```

只查看commit号

```
git log --pretty=oneline
```

查看原来全部历史（重启后）

```
git reflog
```

### 退回上一版本

```
git reset --hard HEAD^
```

任意版本

```
git reset --hard (commit id)
```