---
layout: post
title: Git Simple Reference
tags: [Git, UNIX]
---

# Git Simple Reference
* 从文件系统目录的角度考虑，整个 Git 系统在本地，每个 Repo 只有一个目录，即工作目录，Stage 和 History 都是 Git 系统维护的，从目录系统无法显式看到；想让一个目录成为工作目录有两种方式:

> `git clone repo-url` 同步远程 Repo，并创建名为 repo-name 的目录  
> `git init` 让这个目录成为可被 Git 处理的目录

如果 clone 自一个远程 Repo，则 Git 会自动创建一个 Alias 为 Origin，指向这个远程 Repo，且提交的时候无须显式指明远程 Repo 的名字：`git push`

如果是通过`git init`创建的本地 Repo，则需要添加一个 Origin，`git remote add origin repo-url`

* `git add .` 默认将目录下所有修改过或新增的文件添加到 Stage，但本次 add 之后所做的任何更改，必须重新 add 才有效；add 操作可以指定文件名；可以每一次都使用 `git add .`，Git 只会给有更改或新增的文件添加这一次的 Commit Message

* `git rm filename` 通知 Stage 删除指定文件；如果文件未经过 Git 删除，再次提交时 Git 会把删除操作记为提交队列的下一个操作，提交完当前更改后再次提交，即可提交删除操作；

* `git commit -a -m "message"` 把当前 Stage 暂存的更改作为一次 commit 提交到 History，并得到一个唯一的快照 SHA-1 值作为本次 commit 的ID；-a 参数用于跳过 add 操作直接 commit

* `git commit --amend` 把上一次提交合并当前更改后替换上一次提交

* `git push origin branch-name` 提交到远程 Repo，和 `git clone repo-url` 与 `git pull repo-url` 一样，执行的是 Repo 的同步操作，与版本控制本身无关

* `git reset HEAD~2` HEAD~2 指的是当前分支的最新版本回滚2个版本，也可以使用 SHA-1 值的前若干位；不加参数时，只把 History 更新到 Stage，抹去已有的更改；加上 --soft 参数只把 HEAD 移动到指定的  commit；加上 --hard 参数更新工作目录，抹去所有痕迹；如果不写 commit 名，默认表示 HEAD，通常用`git reset --hard` 实现沙箱；

* `git checkout branch-name commit-hash` 舍弃工作目录中的内容，切换到指定分支的指定版本，因此通常需要 commit 再 checkout；或者使用 `git stash` 暂存工作目录中的内容，需要时再 `git stash apply` 返回暂存的状态；checkout 不显式指定 commit-name 时，将复制 Stage 中的内容，即抹去未 Stage 的更改

* `git merge branch-name` 将指定分支与当前分支合并，以当前分支为准；所谓的 pull 操作就是一次 fetch 操作紧接着一次 merge 操作；fetch 操作被 Git 系统维护而不得到一个显式的工作目录，这是其与 clone 操作的区别
