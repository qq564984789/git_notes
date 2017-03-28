### 在git提交环节，存在三大部分：working tree, index file, commit
- working tree：就是你所工作在的目录，每当你在代码中进行了修改，working tree的状态就改变了。
- index file：是索引文件，它是连接working tree和commit的桥梁，每当我们使用git-add命令来登记后，index file的内容就改变了，此时index file就和working tree同步了。
- commit：是最后的阶段，只有commit了，我们的代码才真正进入了git仓库。我们使用git-commit就是将index file里的内容提交到commit中。
> 每次commit，master分支都会向前移动一步(指向新提交的节点)，同时，每次提交后 HEAD 随着分支一起向前移动。这样，随着你不断提交，master分支的线也越来越长。
### **git diff**
- git diff：是查看working tree与index file的差别的。
- git diff --cached：是查看index file与commit的差别的。
- git diff HEAD：是查看working tree和commit的差别的。（你一定没有忘记，HEAD代表的是最近的一次commit的信息）

### **git branch**
- git branch:查看所有分支。
- git branch <name>:创建新分支
- git checkout <name>:切换分支 
- git checkout -b <name>:创建+切换分支
- git merge <name>:合并某分支到当前分支 
- git branch -d <name>:删除某分支
>Git 又是如何创建一个新的分支的呢？答案很简单，创建一个新的分支指针。比如新建一个 testing 分支，可以使用 git branch 命令：`$ git branch testing`
这会在当前 commit 对象上新建一个分支指针testing。运行git branch 命令，仅仅是建立了一个新的分支，但不会自动切换到这个分支中去。
那么，Git 是如何知道你当前在哪个分支上工作的呢？其实答案也很简单，它保存着一个名为 HEAD 的特别指针。
它是一个指向你正在工作中的本地分支的指针（译注：##将 HEAD 想象为当前分支的别名##）。因此，当前的HEAD指针指向master分支。
当我们现在转换到新建的 testing 分支：
`$ git checkout testing`,
这样 HEAD 就指向了 testing 分支.**因此，在当前分之下的每次commit，分支名会指向当前的commit,HEAD总是指向当前分支名。
（每次提交后 HEAD 随着当前分支一起向前移动）**HEAD 在一次 checkout 之后移动到了另一个分支这条命令做了两件事。它把 HEAD 指针移回到 master 分支，并把工作目录中的文件换成了 master 分支所指向的快照内容

##
- git merge --no-ff -m "merge with no-ff" <name>：将某个分支合并到当前分支，且禁止使用`Fast forward`模式（由--no-ff表示）。
                      由于禁止使用了`Fast forward`模式,所以本次合并要创建一个新的commit，所以加上-m参数，把commit描述写进去。
                      
- 合并分支时，加上--no-ff参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而fast forward合并就看不出来曾经做过合并。



## 
- git add .:添加当前路径下的所有文件
