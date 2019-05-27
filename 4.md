# 版本回退

## 查看版本日记
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

## 退回上一版本
```
git reset --hard HEAD^
```
任意版本
```
git reset --hard (commit id)
```
