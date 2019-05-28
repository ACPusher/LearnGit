# 标签

## 标签基本操作
创建标签（不加参数则是在最近的一次commit上打标签）
```
git tag v1.0 commit id
```
查看全部标签
```
git tag
```
指定标签信息
```
git tag -a <tagname> -m "版本1" commit id
```
查看标签信息
```
git show <tagname>

```
删除标签
```
git tag -d <tagname>
```

## 远程库标签操作
推送单个标签
```
git push origin <tagname> 
```
推送全部标签
```
git push origin --tags
```
删除远程标签
```
git tag -d <tagname>
git push origin :refs/tags/<tagname>
```
