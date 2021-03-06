# 分支的使用

## 分支的基本操作
创建
```
git branch dev
```
切换
```
git checkout dev
```
创建并切换
```
git checkout -b dev
```
**切换分支后看到的工作区和当前分支一致**
查看当前分支（打星号的是当前分支）
```
git branch
```
合并到当前分支
```
git merge dev
```
删除分支
```
git branch -d dev
```

## 解决分支冲突
合并步骤出现"Conflict"字样，可以使用以下语句查看冲突的文件。
```
git status
```
此后修改文件，Git用`<<<<<<<`，`=======`，`>>>>>>>`标记出不同分支的内容。
这里需要注意的是，修改后只会修改主分支上的文件，被合并的分支上的文件不会有变化，因为该合并操作是将从分支合并到主分支。
最后将分支删除即可。
**修改后无需再次合并分支，直接add & commit即可**

## 分支管理策略
整体思路，平时编写的代码存放与dev分支上，比较成熟的代码合并于master分支上，需要注意的是，合并的时候，dev一定要对master的内容是包含关系，否则会引起冲突。
合并时使用以下语句，可以保持dev分支的存在，并且未合并后的commit进行命名。
```
git merge --no-ff -m "merge with no-ff" dev
```
查看分支和commit的历史则可以使用以下的语句，使显示做到尽可能简洁。
```
git log --graph --pretty=oneline --abbrev-commit
```

## Bug分支和Feature分支
在某一分支上作业时，可能有已经add的文件但是不适合现在就进行commit，而此时需要换到另外的分支上进行编辑，我们需要对当前的暂存区进行一个保存，可以使用以下语句。
```
git stash
```
此时查看分支状态可以看到分支树是空的。
处理完后回到该分支使用以下语句可以还原到当时的暂存区。
```
git stash pop
```
如果创建了一个新的分支且已经有文件被进行了add操作，但此时需要删去这个分支的话，就需要用下面的语句强行删除该分支。
```
git branch -D feature1
```
但是此时的文件还是存在的，可以使用以下语句将其移动到现在的位置。
```
git reset HEAD file
```
