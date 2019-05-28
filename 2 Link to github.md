# 连接Github

## 创建
命名后其余保持默认即可。

## 后续指令
关联远程数据库
```
git remote add origin https://github.com/ACPusher/LearnGit.git
```
第一次推送到远程
```
git push -u origin master
```
后续推送到远程
```
git push origin master
```

这里也可以推送别的分支，如

```
git push origin dev
```



## 远程到本地

使用命令如下，这会在当前路径下，创建文件夹。
```
git clone https://github.com/ACPusher/LearnGit.git
```
