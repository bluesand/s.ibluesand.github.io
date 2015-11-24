---
layout: post
title: Git
---

##Git操作命令

* `git config`

```
// 本地Git的一些配置信息

// 全局的配置信息，针对所有工程
git config --global user.name "[name]" 
git config --global user.email "[email]"

// 去掉 global 的话，只针对当前工程 
```

* `git init`

```
//初始化创建工程，--bare表示只建立裸仓库,没有工作区
git init --bare [project]

//Github上可以通过UI手动创建 `New Repository` 
```

* `git clone`

```
//url 支持ssh, http两种协议，ssh支持读写，http只支持读，也就是只能下载
git clone [url]
```

* `git add`

```
//添加file文件到本地暂存区,或者说索引
git add ［file］

//提交本地所有文件
git add .

//如果文件merge冲突修改后，`git add [file]`后标示解决冲突。

//`git stash`可以缓存 `git add`后的文件
```

* `git commit`

```
//索引文件添加到本地仓库,
git commit "[commit message]"

//如果不加 `-m`会进入`VI`模式填写[commit message]
git commit -m "[commit message]"

//`-am`可以合并 `git add`和`git commit`两步
git commit -am "[commit message]"

```

* `git status`

```
//列出本地仓库有改动的文件
```

* `git diff`

```
//显示具体的改动
git diff 

//显示具体某个文件的改动
git diff [file]
```

* `git log`

```
//显示提交记录信息
git log
```

* `git push`

```
//提交文件到远程仓库
git push 

//提交具体本地仓库到远程哪个分支,如：
git push origin master
```

* `git fetch`

```
//获取远程最新文件到本地
git fetch 
```

* `git rebase`

```
//合并本地和远程分支，并保持本地提交在最上面。
git rebase 

//合并
git rebase origin/master
```

* `git branch`

```
//查看本地分支
git branch
```

* `git checkout`

```
//切换分支
git checkout [branch]

//忽略本地的改动
git checkout [file]
```

* `git reset`

```
//当前分支恢复到指定，默认为HEAD分支
git reset [commitId]
```

* `git cherry-pick`

```
//把一个[commit]从一个分支转移到另一个分支.
git checkout [branch]
git cherry-pick ［commitId］

```

* `git revert`

```
//撤销一次提交
git revert [commitId]
```

* `git remote`

```
//远程仓库操作命令
git remote

//增加本地的一个`origin`仓库,连接到远程的[url]
git remote add origin [url]
```

* `git tag`

```
//给分支打tag
git tag [version]
```

* `git pull`

```
//相当于`git fetch` + `git merge`
//合并代码推荐使用 `git fetch` + `git rebase`
```

##Git简单开发模式

保证只有一个`master`分支用于开发仓库，开发人员每次`push`代码到自己的开发分支`temp_username`，然后`code review`后没有问题, `merge`到`master`,并删除当前`temp`分支，所有功能开发完毕，`bug`修改完毕后，`checkout`分支`release`版本。如果`release`版本有紧急`bug`，`fix bug`当前`release`版本后，同时`cherry-pick`一份到`master`分支上。如果有`feature`分支，比如针对运营的版本，也是从`master`上`checkout`出去修改。  
总之保证`master`始终是最新的开发主干分支，其他是`release`,`feature`，`temp`分支。

```
git clone [url]
`开发或者修改bug`
git add .
git commit -m "commit message"
git push origin temp_username
```
---

```
`代码审核不通过`
`开发或者修改bug，注意:提交后不要fetch并rebase代码了`
git add .
git commit -m "commit message"
git push origin temp_username

`代码审核通过`
merge到master
git push origin :temp_username //删除分支
```
---

```
git fetch
git rebase origin/master

`解决冲突`
git add .
git rebase --continue
`反复解决冲突，直到没有冲突`

git add .
git commit -m "commit message"
git push origin temp_username
```

















