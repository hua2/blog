---
title: " Git 基本命令\t\t"
tags:
  - 其他
id: '92'
date: 2018-07-24 17:31:43
---

初始化一个Git仓库，使用git init命令。 添加文件到Git仓库，分两步：

*   命令git add <file>,把文件添加到仓库;注意，可反复多次使用，添加多个文件；
*   命令git commit,把文件提交到仓库: git commit-m <message> (-m后面输入的是本次提交的说明)

命令git status: 随时掌握工作区的状态 命令git diff: 可以查看不同 命令git log: 可以查看提交历史，以便确定要回退到哪个版本(加上--pretty=oneline参数) 命令git reflog: 查看命令历史 命令git reset --hard commit\_id: HEAD指向的版本就是当前版本(上一个版本就是HEAD^)

#### 撤销修改:  自修改后还没有被放到暂存区，想直接丢弃工作区的修改时，用命令git checkout -- file。

添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，用命令git checkout -- file。 git rm用于删除一个文件 ****克隆仓库****，首先必须知道仓库的地址，然后使用git clone命令克隆。 **Git鼓励大量使用分支：** 查看分支：git branch 创建分支：git branch <name> 切换分支：git checkout <name> 创建+切换分支：git checkout -b <name> 合并某分支到当前分支：git merge <name> 删除分支：git branch -d <name> 用git log --graph命令：可以看到分支合并图。 --no-ff参数，表示禁用Fast forward：合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。 修复bug时，我们会通过创建新的bug分支进行修复，然后合并，最后删除； 当手头工作没有完成时，先把工作现场git stash一下，然后去修复bug，修复后，再git stash pop，回到工作现场。 (stash功能，可以把当前工作现场“储藏”起来，等以后恢复现场后继续工作,用git stash list命令看看，刚才的工作现场存到哪去了？ Git把stash内容存在某个地方了，但是需要恢复一下，有两个办法：

*   用git stash apply恢复，但是恢复后，stash内容并不删除，你需要用git stash drop来删除；
*   用git stash pop，恢复的同时把stash内容也删了 )

开发一个新feature，最好新建一个分支； 如果要丢弃一个没有被合并过的分支，可以通过git branch -D <name>强行删除。 查看远程库的信息，用git remote;  用git remote -v显示更详细的信息